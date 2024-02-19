<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tattoo Booking Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: rgb(0, 0, 0); /* Almost black background */
            color: white; /* White text color */
            margin-left: 10px; /* Small grey side margin on the left */
            margin-right: 10px; /* Small grey side margin on the right */
        }

        #header {
            width: 100%;
            height: 1px; /* Set the height of the line */
            box-shadow: 0 2px 5px rgba(255, 255, 255, 0.1); /* Box shadow for the line */
            margin-bottom: 20px; /* Add space between the header and the title */
        }

        #formContainer {
            display: flex;
            align-items: flex-start; /* Align to the top of the container */
            justify-content: flex-start; /* Justify content to the left */
            min-height: 100vh;
            max-width: 800px;
            margin: 20px auto 0; /* Add margin-top for space between the top and the title */
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.9); /* Almost black background with adjustable alpha for transparency */
            border-radius: 0; /* 90-degree corners */
        }

        form {
            width: 100%;
        }

        h2 {
            text-align: left;
            font-weight: normal; /* Use a thinner font weight */
            color: #bbb; /* Light grey heading text color */
            margin-bottom: 10px; /* Add space between title and form */
            margin-top: 0; /* Adjust margin-top */
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #bbb; /* Light grey label text color */
        }

        input, select, textarea {
            width: calc(100% - 16px);
            padding: 8px;
            margin-bottom: 16px;
            box-sizing: border-box;
            border: 1px solid #444; /* Dark grey border */
            border-radius: 4px;
            background-color: #222; /* Almost black background for input fields */
            color: #bbb; /* Light grey text color for input fields */
        }

        /* Add placeholder styling */
        input::placeholder,
        textarea::placeholder {
            color: #444; /* Dark grey color for placeholder text */
        }

        button {
            background-color: rgb(29, 185, 84); /* Spotify green */
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 8px; /* Rounded corners */
            cursor: pointer;
        }

        button:hover {
            background-color: rgb(0, 100, 0); /* Darker forest green on hover */
        }

        #referenceImagesContainer {
            width: fit-content;
            display: inline-block;
            padding: 10px;
            border: 1px solid #888;
            border-radius: 8px;
            background-color: transparent; /* Transparent background for reference images button */
            color: #bbb; /* Light grey text color for reference images button */
            cursor: pointer;
            margin-top: 20px; /* Add space between title and reference images */
        }

        #referenceImagesContainer::before {
            content: "+"; /* Plus symbol */
            font-size: 18px;
            font-weight: bold;
            margin-right: 5px;
        }

        #referenceImagesInput {
            display: none;
        }
    </style>
</head>
<body>

    <div id="header"></div> <!-- Header with box shadow -->

    <div id="formContainer">

        <form id="bookingForm" action="submit.php" method="post" onsubmit="validateForm(event)">
            <h2>Tattoo Booking Form</h2>

            <label for="fullName">Full Name *</label>
            <input type="text" id="fullName" name="fullName" required>

            <label for="email">Email *</label>
            <input type="email" id="email" name="email" required>

            <label for="pronouns">Pronouns</label>
            <input type="text" id="pronouns" name="pronouns">

            <label for="description">Description *</label>
            <textarea id="description" name="description" rows="4" required></textarea>

            <label for="placement">Placement *</label>
            <input type="text" id="placement" name="placement" required>

            <label for="size">Size *</label>
            <input type="text" id="size" name="size" required>

            <label for="budget">Budget</label>
            <input type="text" id="budget" name="budget">

            <label for="availability">Availability</label>
            <input type="text" id="availability" name="availability">

            <div id="referenceImagesContainer" onclick="document.getElementById('referenceImagesInput').click();">
                Reference Images
                <input type="file" id="referenceImagesInput" name="referenceImages" accept="image/*" multiple>
            </div>

            <button type="submit">Submit</button>
        </form>

    </div>

    <script>
        function validateForm(event) {
            var fullName = document.getElementById('fullName').value;
            var email = document.getElementById('email').value;
            var description = document.getElementById('description').value;
            var placement = document.getElementById('placement').value;
            var size = document.getElementById('size').value;

            if (!fullName || !email || !description || !placement || !size) {
                alert('Please fill in all required fields.');
                event.preventDefault();
            }
        }
    </script>

</body>
</html>

