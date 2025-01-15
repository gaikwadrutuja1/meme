<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Meme Generator by Rutuja Gaikwad</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background: url('https://source.unsplash.com/1600x900/?nature,funny') no-repeat center center fixed;
            background-size: cover;
            color: white;
            height: 100vh;
            margin: 0;
        }
        h1 {
            font-size: 3rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }
        img {
            width: 80%;
            max-width: 600px;
            border-radius: 10px;
            margin-top: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }
        button {
            background-color: #4CAF50;
            color: white;
            font-size: 16px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
        }
        button:hover {
            background-color: #45a049;
        }
        .content-container {
            background-color: rgba(0, 0, 0, 0.6); /* Semi-transparent background for text and buttons */
            padding: 30px;
            border-radius: 10px;
            max-width: 700px;
            margin: 0 auto;
        }
    </style>
</head>
<body>
    <div class="content-container">
        <h1>Random Meme Generator by Rutuja Gaikwad</h1>
        <img id="memeImage" src="" alt="Meme will appear here!" />
        <br>
        <button onclick="fetchMeme()">Get New Meme</button>
    </div>

    <script>
        // Function to fetch a random meme from the API
        async function fetchMeme() {
            try {
                const response = await fetch('https://meme-api.com/gimme');
                const data = await response.json();
                const memeUrl = data.url;

                // Update the image source with the new meme
                const memeImage = document.getElementById('memeImage');
                memeImage.src = memeUrl;
            } catch (error) {
                console.error('Error fetching meme:', error);
            }
        }

        // Load the first meme when the page loads
        window.onload = fetchMeme;
    </script>
</body>
</html>
