# HDAnime.org Cover Fetching API

This API allows you to fetch anime covers from HDAnime.org using GraphQL queries. You can use this API to retrieve cover images for specific anime titles and integrate them into your applications or websites. Here's how to use it:

## Usage

To fetch an anime cover, use the `fetch_anime_cover` function provided in the `fetch_anime_cover.php` file. Simply pass the anime name as an argument, and it will return the cover image URL.

Example:

```php
$animeName = "Your_Anime_Title"; // Replace with the anime title.
$cover = fetch_anime_cover($animeName);

if ($cover) {
    echo '<img src="' . $cover . '" alt="' . $animeName . ' Cover">';
} else {
    echo '<img src="path_to_placeholder_image" alt="Default Cover">';
}
```

You can customize it to your needs, and feel free to contribute to its development.
