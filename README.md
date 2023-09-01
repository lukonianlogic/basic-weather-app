# basic-weather-app
Just a basic weather app

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather App</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <style>
        body {
            background-color: #f7f7f7;
        }

        .container {
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color: #007bff;
        }

        #weatherMessage {
            font-size: 20px;
            margin-top: 20px;
        }

        #weatherIcon {
            width: 100px;
            height: 100px;
        }

        /* Add more custom CSS styles here if needed */
    </style>
</head>
<body>
    <div class="container mt-5">
        <div class="row">
            <div class="col-md-6 offset-md-3 text-center">
                <h1>Weather App</h1>
                <div class="form-group">
                    <label for="weatherInput">Enter the weather:</label>
                    <input type="text" class="form-control" id="weatherInput">
                </div>
                <button class="btn btn-primary" id="checkWeather">Check Weather</button>
                <div id="weatherMessage" class="mt-3"></div>
                <img src="" id="weatherIcon" alt="Weather Icon">
            </div>
        </div>
    </div>

    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.6/dist/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <script>
        // JavaScript code for checking weather and displaying a message
        document.getElementById("checkWeather").addEventListener("click", function () {
            let weatherInput = document.getElementById("weatherInput").value;
            let weatherMessage = document.getElementById("weatherMessage");
            let weatherIcon = document.getElementById("weatherIcon");

            // Convert the input to lowercase for case-insensitive matching
            let lowercaseInput = weatherInput.toLowerCase();

            // Check if the input matches any of the specified weather conditions
            if (lowercaseInput.includes('rain') || lowercaseInput.includes('thunderstorm') || lowercaseInput.includes('drizzle')) {
                weatherMessage.innerHTML = '<p>Grab your umbrella ☂️</p>';
                weatherIcon.src = 'https://cdn.iconscout.com/icon/free/png-256/rain-forecast-weather-wet-umbrella-umbrella-36354.png';
            } else if (lowercaseInput.includes('sunshine') || lowercaseInput.includes('sunny') || lowercaseInput.includes('clear')) {
                weatherMessage.innerHTML = '<p>Wear your sunglasses 😎</p>';
                weatherIcon.src = 'https://cdn.iconscout.com/icon/free/png-256/sunglasses-2959243-2476395.png';
            } else {
                weatherMessage.innerHTML = '<p>Invalid input. Please enter a valid weather condition.</p>';
                weatherIcon.src = ''; // Clear the icon
            }
        });
    </script>
</body>
</html>
