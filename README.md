# FileLoader: A Flash Preloader &amp; Container File

FileLoader is a simple, lightweight, easy-to-implement FLA/SWF file that acts as a preloader and container for files. It is made to load a specified URL, can enable "cache busting", and provides the ability to change the hex color of the preloader and text. It can load any type of file that the built-in Loader class loads (SWF, JPG, PNG, GIF).

### Instructions

To use FileLoader, simply update any/all of the customizable variables located on the aptly-named "Customizable Variables" layer of the source FLA. These variables include:

- **contentURL** _(String)_: URL path of the content you wish to load into FileLoader. (Default = "")
- **tintHex** _(uint)_: Hex value to tint the preloader and error message. (Default = "0x000000")
- **cacheBuster** _(Boolean)_: Enables/Disables "cache busting" on your content. (Default = "false")

Once the variables are updated, just export the SWF and it's ready to be embedded into your HTML page for the web.

### Notes

- FileLoader is set up to resize itself to 100% of the stage width and height, making it flexible to be used at any size. This means you don't have to worry about changing the dimensions of the file, and when embedding it into your HTML page, you can specify any width and height you wish. The Preloader and Load Error (if applicable) will automatically center themselves to the stage. The content, however, has no special positioning logic, and will be placed at the (0,0) point of the stage. Thus, it is intended that this file will be embedded at the exact size of the content you're loading into it, as this file is only intended to be a preloader and container for the contents of one file.
- The Preloader and Load Error elements (where applicable) are automatically added to and removed from the file when needed. Your content will automatically be placed into the file when it's loaded, and be the only item on the stage at that point. You don't have to do anything special to get your content to display other than specifying a valid content URL.
- When you're ready to post the files to your website, just make sure you upload this file along with the content it loads. Also, make sure your pathing is set up appropriately for the content URL or your content may not load correctly.
- If you update or change any of the MovieClips in the library, or update, append or change any of the code in the main Actions layer, this file may break. If you know what you're doing with Flash and ActionScript, you shouldn't have any problem figuring out how things work and can be edited. If you're a beginner or novice, you may have a harder time editing. With that said, edit the non-customizable elements at your own risk.
- If the "cacheBuster" variable is set to "true", a random 8-digit ID will be appended as a query string to the "contentURL" variable (i.e. "photo.jpg?id=12345678"). When the cache buster is enabled, it will force the FileLoader to load a fresh version of the content URL each time it is loaded. This is helpful if you are posting your Flash content on a server with its own cache settings that would result in updated content not being immediately visible until the server cache clears. If this variable is set to "false", no ID will be appended to the content URL, and the loaded content will be cached as normal.
- Important: Use the cache busting sparingly and only when necessary, as it may end up bogging down the server with unnecessary calls to the server to reload the content.

### License

FileLoader is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License. For more information about this license, visit: http://creativecommons.org/licenses/by-sa/3.0/
