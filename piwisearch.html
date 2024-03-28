<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <style>
        /* CSS Styles */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        h1 {
            margin-top: 50px;
        }

        .search-container {
            margin-top : 50px;
            display: flex;
            justify-content: center;
        }

        .search-container input[type=text] {
            padding : 10px;
            width : 50%;
            border: 1px solid #ccc;
            border-radius : 5px;
            outline: none;
        }

        .search-container select {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            outline: none;
            margin-right: 10px;
        }

        .search-container button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border-radius : 5px;
            margin-right : 10px;
            margin-left : 10px;
        }

        .search-container button:hover {
            background-color : #0056b3;
        }
        #imageContainer img {
            height: 200px;
            width: auto;
            margin : 10px;
        }
        #infoIconContainer {
            position: relative;
            display: inline-block;
        }

        #infoIcon {
            cursor: pointer;
        }

        #infoBox {
            display: none;
            position: absolute;
            background-color: #f9f9f9;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
            z-index: 1;
            top: 150%;
            left: 50%;
            transform: translateX(-50%);
            width: 500px;
            text-align: center;
        }

        #infoIconContainer:hover #infoBox {
            display: block;
        }


    </style>
    <title>Piwigo Search Engine</title>
</head>
<body>
    <h1>Piwisearch</h1>
        <!-- Information Icon and Info Box -->
    <div id="infoIconContainer">
        <i id="infoIcon" class="fas fa-info-circle"></i>
        <div id="infoBox">
            This page was made in order to understand multiple aspects of the Piwigo environnement and API. <br>
             here's a short list of what's been made and what's still to improve. <br><br>
             Available to date : <br>
             - Search an image in your piwigo galery by name and tag (tags combinaisons car be separated by a , in the search bar).<br>
             - Sort the result by different orders (date_available, date_creation, hit (views amount), name) and by Ascending and Descending directions.<br>
             - Choose to display up to 500 medias (Api limit).<br><br>
             Missing implements and buglist:<br>
             - When making a request, the server will respond by sending your medias with an integer id going from 0 to your selected amount -1 which leads to the next issue.<br>
             - If descendant order is selected, it will only reverse the actual  selection (example : If there are 200 medias in your galery and you choose to only display half of it,  selecting descending order won't display the other half but will just display in reverse the 100 actual ones).<br>
             - pwg.images.search and pwg.tags.search.getImages both uses paginations with a page method that's not implemented yet which also causes the above issues.<br>
             - When searching for medias by tags, the tag_mode_and option hasn't been implemented, so you won't be able to search for  medias with a tag OR another, but will make the seach with the AND iteration by default.
             
        </div>
    </div>
    <!-- Search Type Form -->
    <div class="search-container">
        <select id="searchType">
            <option value="name">By Name</option>
            <option value="tag">By Tag</option>
        </select>
        <input type="text" id="searchInput" placeholder="Search.." name="search">
        <button id="searchButton">Search</button>
         <!-- Order Form -->
        <select id="sortOrder">
            <option value="date_available">Date Available</option>
            <option value="date_creation">Date Creation</option>
            <option value="hit">Number of Views</option>
            <option value="name">Name</option>
        </select>
        <!-- Direction Form -->
        <select id="sortDirection">
            <option value="asc">Ascending</option>
            <option value="desc">Descending</option>
        </select>
        <input type="number" id="perPage" name="perPage" min="1" max="500" value="100" placeholder="Per Page">
    </div>
    <!-- Container for Images -->
    <div id="imageContainer"></div>

    <!-- JavaScript Code -->
    <script>
// Function to execute on Search Button Click
$('#searchButton').click(function() {
    // Get search query, search type, order, direction and perPage from user input
    let query = $('#searchInput').val().trim();
    let searchType = $('#searchType').val();
    let sortOrder = $('#sortOrder').val();
    let sortDirection = $('#sortDirection').val();
    let perPage = $('#perPage').val();

    // Check if query is not empty
    if (query !== '') {
        // Construct API URL based on search type
        let protocol = window.location.protocol;
        let domain = window.location.host;
        let path = window.location.pathname;
        let apiUrl;

        if (searchType === 'name') {
            apiUrl = protocol + "//" + domain + "/piwigo/ws.php?format=json&method=pwg.images.search&query=" + encodeURIComponent(query);
        } else if (searchType === 'tag') {
            // Split tags and encode them for URL
            let tags = query.split(',').map(tag => encodeURIComponent(tag.trim()));
            // Construct tag parameters for API URL
            let tagParams = tags.map(tag => "tag_name[]=" + tag).join('&');
            apiUrl = protocol + "//" + domain + "/piwigo/ws.php?format=json&method=pwg.tags.getImages&" + tagParams;
        }

        // Append perPage amount and sort order to apiUrl
        apiUrl += "&per_page=" + perPage + "&order=" + sortOrder;
        console.log(apiUrl);

        // Make GET request to Piwigo API
        $.get(apiUrl, function(data, status) {
            if (status === "success") {
                // Parse JSON response data
                data = JSON.parse(data);
                // Check if API call was successful
                if (data.stat === "ok") {
                    // Extract images data from API response
                    let images = data.result.images;
                    // Clear previous images from container
                    $('#imageContainer').empty();
                    console.log(data);
                    // Iterate through images and display them as thumbnails depending on direction order
                    //Ascending Iteration
                    if (sortDirection === 'asc') {
                        images.forEach(function(image) {
                            let imageUrl = image.derivatives.thumb.url;
                            let imgElement = $('<img>').attr('src', imageUrl);
                            $('#imageContainer').append(imgElement);
                        });
                    //Descending Iteration
                    } else if (sortDirection === 'desc') {
                        for (let i = images.length - 1; i >= 0; i--) {
                            let imageUrl = images[i].derivatives.thumb.url;
                            let imgElement = $('<img>').attr('src', imageUrl);
                            $('#imageContainer').append(imgElement);
                        }
                    }
                } else {
                    // Log error message if API call failed
                    console.log("Error:", data.message);
                }
            } else {
                // Log error if request failed
                console.log("Request failed with status:", status);
            }
        }).fail(function() {
            // Log error if connection to server failed
            console.log("Error: Unable to connect to the server.");
        });
    } else {
        // Alert user if search term is empty
        alert("Please enter a search term.");
    }
});
</script>
</body>
</html>
