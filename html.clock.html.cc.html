<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Clock GIF Uploader</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        #console {
            width: 100%;
            height: 200px;
            border: 1px solid #ccc;
            padding: 10px;
            font-family: monospace;
            background-color: #f5f5f5;
            overflow-y: auto;
            white-space: pre-wrap;
        }
        #progress {
            margin-top: 10px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
    </style>
</head>
<body>

    <h1>GitHub Clock GIF Uploader</h1>

    <!-- Input for GitHub API Token -->
    <input type="text" id="apiToken" placeholder="Enter GitHub API Token" />
    
    <!-- Button to start uploading -->
    <button onclick="uploadGIFs()">Start Uploading</button>

    <!-- Console for progress display -->
    <div id="console"></div>
    
    <div id="progress"></div>

    <!-- Include gif.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gif.js/0.2.0/gif.min.js"></script>


<script src="https://cdn.jsdelivr.net/npm/gif.js@0.2.0/dist/gif.min.js"></script>

<script src="https://cdn.jsdelivr.net/npm/gif.js@0.2.0/dist/gif.worker.js"></script>

    <script>
        // GitHub repository and directory setup
        const GITHUB_API_URL = 'https://api.github.com/repos/DrMineword/databasd_and_randomthings_wscd/contents/clock/digita/gifs/lightorange/';
        const MAX_RETRIES = 3;
        const GIF_DELAY = 1000; // 1 second delay for each gif upload

        // Function to write messages to the console area in the HTML
        function logMessage(message) {
            const consoleDiv = document.getElementById('console');
            consoleDiv.innerText += message + '\n';
            consoleDiv.scrollTop = consoleDiv.scrollHeight;
        }

        // Function to upload the GIF to GitHub
        async function uploadToGitHub(fileName, gifBase64, token) {
            const url = GITHUB_API_URL + fileName;
            const headers = {
                'Authorization': `${token}`,
                'Content-Type': 'application/json'
            };

            const payload = {
                message: `Add clock GIF ${fileName}`,
                content: gifBase64,
                branch: 'main'  // Default branch
            };

            try {
                const response = await fetch(url, {
                    method: 'PUT',
                    headers: headers,
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    throw new Error(`Error uploading ${fileName}: ${response.statusText}`);
                }

                logMessage(`Uploaded ${fileName} successfully!`);
            } catch (error) {
                logMessage(`Failed to upload ${fileName}: ${error.message}`);
            }
        }

        // Function to generate GIF for a given hour and minute
        function generateGIF(hour, minute) {
            return new Promise((resolve, reject) => {
                const gif = new GIF({
                    workers: 2,
                    quality: 10
                });

                const canvas = document.createElement('canvas');
                const ctx = canvas.getContext('2d');
                canvas.width = 200;
                canvas.height = 100;

                const drawClock = (showColon) => {
                    ctx.clearRect(0, 0, 200, 100);
                    ctx.fillStyle = '#FFD580'; // Light orange color
                    ctx.font = '80px monospace';
                    ctx.textAlign = 'center';
                    ctx.textBaseline = 'middle';

                    const colon = showColon ? ':' : ' ';
                    const timeText = `${hour.toString().padStart(2, '0')}${colon}${minute.toString().padStart(2, '0')}`;
                    ctx.fillText(timeText, 100, 50);
                };

                // Add frames for the GIF (blink the colon)
                for (let i = 0; i < 6; i++) {
                    drawClock(i % 2 === 0);
                    gif.addFrame(canvas, { delay: 750 });
                }

                gif.on('finished', function (blob) {
                    const gifBase64 = blobToBase64(blob);
                    resolve(gifBase64);
                });

                gif.render();
            });
        }

        // Convert GIF Blob to Base64
        function blobToBase64(blob) {
            return new Promise((resolve, reject) => {
                const reader = new FileReader();
                reader.onloadend = () => resolve(reader.result.split(',')[1]);
                reader.onerror = reject;
                reader.readAsDataURL(blob);
            });
        }

        // Function to upload all the GIFs
        async function uploadGIFs() {
            const token = document.getElementById('apiToken').value;
            if (!token) {
                logMessage('Error: GitHub API Token is required');
                return;
            }

            let totalFiles = 0;
            let uploadedFiles = 0;

            // Loop through all hours and minutes
            for (let hour = 0; hour < 24; hour++) {
                for (let minute = 0; minute < 60; minute++) {
                    const fileName = `${String(hour).padStart(2, '0')}/${String(minute).padStart(2, '0')}.gif`;
                    logMessage(`Generating GIF for ${fileName}...`);

                    try {
                        // Generate the GIF
                        const gifBase64 = await generateGIF(hour, minute);

                        // Upload the GIF to GitHub
                        await uploadToGitHub(fileName, gifBase64, token);

                        uploadedFiles++;
                        logMessage(`Progress: ${uploadedFiles}/${24 * 60} files uploaded.`);
                    } catch (error) {
                        logMessage(`Error generating/uploading ${fileName}: ${error.message}`);
                    }

                    // Update progress bar (optional)
                    const progress = Math.floor((uploadedFiles / (24 * 60)) * 100);
                    document.getElementById('progress').innerText = `Progress: ${progress}%`;

                    // Delay between uploads to prevent rate-limiting
                    await new Promise(resolve => setTimeout(resolve, GIF_DELAY));
                }
            }

            logMessage('All GIFs uploaded successfully!');
        }
    </script>

</body>
</html>
