# Piwigo API Exploration

This page was created to explore various aspects of the Piwigo environment and API.

## Features

### Available Features

- **Search Functionality**: Search for images in your Piwigo gallery by name and tag. Tags combinations can be separated by commas in the search bar.
- **Sorting Options**: Sort the search results by different criteria such as date_available, date_creation, hit (views amount), and name. Sorting can be done in ascending or descending order.
- **Display Control**: Choose to display up to 500 items (API limit).

### Missing Implementations and Buglist

- **Server Response Issue**: When making a request, the server responds by sending media with an integer ID ranging from 0 to the selected amount minus one, leading to the following indexing issues.
- **Descending Order Bug**: If descending order is selected, it reverses the actual selection instead of displaying the full set of media items in descending order.
- **Pagination Issue**: The pagination method for `pwg.images.search` and `pwg.tags.search.getImages` is not implemented, causing issues with large result sets.
- **Tag Search Functionality**: The `tag_mode_and` api method for searching media by tags hasn't been implemented, causing the search to stay by default to AND combinaisons instead of allowing OR combinations.

## How to Use

You can either use .php or .html files depending on your web server, the piwigo folder should be in the same directory as the piwisearch file or it will cause issues with the apiUrl variable.

## 

- Tison Marceau
