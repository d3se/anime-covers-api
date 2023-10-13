# HDAnime.org Cover Fetching API

This API allows you to fetch anime covers from HDAnime.org. You can use this API to retrieve cover images for specific anime titles and integrate them into your applications or websites. Note that it is season sensitive, ignores most typos and is not Case Sensitive. Here's how to use it:

## Usage

To fetch an anime cover, make an HTTP GET request to the following endpoint:

```
https://hdanime.org/api/fetch_cover.php?anime_name=Your_Anime_Title
```

Replace `Your_Anime_Title` with the title of the anime for which you want to retrieve the cover image.

The response will contain an HTML image tag with the cover image. If no cover is found, a placeholder image or a default image URL is provided.

### Example in PHP

You can use PHP to send a request to the API and display the cover image:

```php
<?php
$animeName = "Your_Anime_Title"; // Replace with the anime title.
$apiUrl = "https://hdanime.org/api/fetch_cover.php?anime_name=" . urlencode($animeName);

// Make a GET request to the API
$response = file_get_contents($apiUrl);

if ($response) {
    echo $response;
} else {
    // Handle the case where no cover is found
    echo '<img src="path_to_placeholder_image" alt="Default Cover">';
}
?>
```

### Example in JavaScript (Client-Side)

You can use JavaScript to call the API and display the cover image on a web page:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Anime Cover Example</title>
</head>
<body>
    <h1>Anime Cover</h1>
    <div id="animeCoverContainer"></div>

    <script>
        const animeName = "Your_Anime_Title"; // Replace with the anime title.
        const apiUrl = `https://hdanime.org/api/fetch_cover.php?anime_name=${encodeURIComponent(animeName)}`;

        // Create an image element and set its source to the API endpoint
        const animeCover = document.createElement('img');
        animeCover.src = apiUrl;
        animeCover.alt = `${animeName} Cover`;

        // Append the image to a container in your HTML
        const container = document.getElementById('animeCoverContainer');
        container.appendChild(animeCover);
    </script>
</body>
</html>
```
