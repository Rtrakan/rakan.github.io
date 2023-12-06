<html>
    <head>
        <style>
            h1,h2{
                text-align: center;
            }
            textarea{
                margin-left: 5%;
                margin-right: 5%;
                width: 39%;
                font-size: 24px;
                height: 600px;
                resize: none;
            }
            *{
                font-family: 'Verdana';
            }
            @font-face {
                font-family: YZIDI;
                src: url(YZIDI.ttf);
            }
            #braille{
                font-family: YZIDI, Verdana;
            }
        </style>
        <title>Yezidi Transliterator</title>
        <script>
            document.addEventListener('DOMContentLoaded', function(){ 
                var typingTimer
                var doneTypingInterval = 1000
                var $inuk = document.getElementById("inuk")
                var $braille = document.getElementById("braille")
                $inuk.addEventListener('keyup', inukFunction)
                function inukFunction () {
                    inuk = $inuk.value.replace(/E/g, "𐺀").toLowerCase()

                    for(e of Object.keys(inukKey)){
                        var myRegExp = new RegExp(e, 'g')
                        inuk = inuk.replace(myRegExp, inukKey[e])
                    }
                    $braille.value = "" + inuk
                }

                inukKey = {
                    " ي": "𐺨 ",
                    " ê": " 𐺀𐺩",
                    "ا'": "𐺗𐺀",
                    "ئ": "𐺩",
                    "we": "𐺣",
                    "ت" : "𐺄",
                    "ا": "𐺀",
                    "ب": "𐺁",
                    "ج": "𐺆",
                    "'": "𐺈",
                    "چ": "𐺇",
                    "د": "𐺋",
                    "ئه": "𐺦",
                    "ى": "𐺩",
                    "ف": "𐺙",
                    "ژ": "𐺟",
                    "ح": "𐺉",
                    "ه": "𐺧",
                    "i": "",
                    "ي": "𐺨",
                    "گ": "𐺐",
                    "ك": "𐺝",
                    "ل": "𐺠",
                    "م": "𐺡",
                    "ن": "𐺢",
                    "ؤ": "𐺥",
                    "p'": "𐺃",
                    "پ": "𐺂",
                    "ق": "𐺜",
                    "ر": "𐺍",
                    "س": "𐺑",
                    "ش": "𐺒",
                    "ط": "𐺕",
                    "و": "𐺣",
                    "وو": "𐺣𐺣",
                    "ڤ": "𐺛", //?
                    "و": "𐺤",
                    "خ": "𐺊",
                    "ي": "𐺨",
                    "ز": "𐺏",
                     
                    "'": "𐺗",
                }
            }, false);
        </script>
    </head>
    <body>
        <h1>Yezidi Script Converter</h1>
        <textarea spellcheck="false" id="inuk" placeholder="enter Latin text" style="direction:ltr"></textarea>
        <textarea contenteditable="false" id="braille" placeholder="Yezidi script output here" style="direction:rtl"></textarea>
    </body>
</html>
