
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Header Website</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 10px;
            text-align: center;
        }

        nav {
            display: flex;
            justify-content: center;
            background-color: #555;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            padding: 10px 20px;
            display: inline-block;
        }

        nav a:hover {
            background-color: #777;
        }




           font-family: 'Arial', sans-serif;
            text-align: center;
            margin: 50px;
            background-color: #add8e6; /* Warna biru muda */
            color: #000; /* Warna hitam */
        }

        h1 {
            color: #000; /* Warna hitam */
        }

        label {
            font-weight: bold;
        }

        input {
            padding: 10px;
            width: 200px;
        }

        button {
            padding: 10px;
            cursor: pointer;
            background-color: #000; /* Warna hitam */
            color: #fff; /* Warna putih */
            border: none;
        }

        p {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <header>
        <h1>APLIKASI NDI MA BACA KODE MORSE KE HURUF , HURUF KE KODE MORSE</h1>
<h1>DHEGAN AL KAIS QURESHY</h1>
    </header>

    <nav>
        <a href="#">MAJA</a>
        <a href="#">LABO</a>
        <a href="#">DAHU</a>
        <a href="#">RINGA</a>
    </nav>
<h1></h1>
<center>
<h1>Huruf Ke Kode Morse</h1>

    <label for="textInput">Tau Tunti:</label>
    <input type="text" id="textInput" placeholder="Contona: a">

    <button onclick="translateToMorse()">Rubah ndadi Kode Morse</button>

    <p id="outputMorse"></p>


    <h1>Kode Morse Ke Huruf</h1>

    <label for="morseInput">Tau Kode Morse:</label>
    <input type="text" id="morseInput" placeholder="Contona: .- -... -.-. .-">

    <button onclick="translateToText()">Rubah ndadi Huruf</button>

    <p id="outputText"></p>

    <script>
        // Fungsi untuk menerjemahkan huruf ke kode Morse
        function translateToMorse() {
            const textInput = document.getElementById("textInput").value.trim().toUpperCase();
            const outputMorse = document.getElementById("outputMorse");

            if (textInput === "") {
                outputMorse.textContent = "Silakan masukkan teks.";
                return;
            }

            const letterToMorse = {
                "A": ".-", "B": "-...", "C": "-.-.", "D": "-..", "E": ".",
                "F": "..-.", "G": "--.", "H": "....", "I": "..", "J": ".---",
                "K": "-.-", "L": ".-..", "M": "--", "N": "-.", "O": "---",
                "P": ".--.", "Q": "--.-", "R": ".-.", "S": "...", "T": "-",
                "U": "..-", "V": "...-", "W": ".--", "X": "-..-", "Y": "-.--",
                "Z": "--..",
                "0": "-----", "1": ".----", "2": "..---", "3": "...--", "4": "....-",
                "5": ".....", "6": "-....", "7": "--...", "8": "---..", "9": "----."
            };

            const characters = textInput.split("");
            let morseCode = "";

            for (const character of characters) {
                if (letterToMorse.hasOwnProperty(character)) {
                    morseCode += letterToMorse[character] + " ";
                } else {
                    morseCode += "? "; // Karakter tidak dikenal
                }
            }

            outputMorse.textContent = morseCode.trim();
        }
    </script>
    <script>
        // Fungsi untuk menerjemahkan kode Morse ke teks
        function translateToText() {
            const morseInput = document.getElementById("morseInput").value.trim();
            const outputText = document.getElementById("outputText");

            if (morseInput === "") {
                outputText.textContent = "Silakan masukkan kode Morse.";
                return;
            }

            const morseCode = {
                ".-": "A", "-...": "B", "-.-.": "C", "-..": "D",
                ".": "E", "..-.": "F", "--.": "G", "....": "H",
                "..": "I", ".---": "J", "-.-": "K", ".-..": "L",
                "--": "M", "-.": "N", "---": "O", ".--.": "P",
                "--.-": "Q", ".-.": "R", "...": "S", "-": "T",
                "..-": "U", "...-": "V", ".--": "W", "-..-": "X",
                "-.--": "Y", "--..": "Z",
                "-----": "0", ".----": "1", "..---": "2", "...--": "3",
                "....-": "4", ".....": "5", "-....": "6", "--...": "7",
                "---..": "8", "----.": "9"
            };

            const words = morseInput.split("   "); // Pemisahan kata menggunakan tiga spasi
            let translatedText = "";

            for (const word of words) {
                const letters = word.split(" ");
                for (const letter of letters) {
                    if (morseCode.hasOwnProperty(letter)) {
                        translatedText += morseCode[letter];
                    } else {
                        translatedText += "?"; // Karakter tidak dikenal
                    }
                }
                translatedText += " ";
            }

            outputText.textContent = translatedText.trim();
        }
    </script>
</center>
</body>
</html>
