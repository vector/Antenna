Antenna for ExpressionEngine 1 & 2
========

**Antenna** is a plugin that will generate the exact, most up-to-date YouTube or Vimeo embed code available. It also gives you access to the video's title, its author, the author's YouTube/Vimeo URL, and a thumbnail. All you have to do is pass it a single URL. 

You can also output various pieces of metadata about the YouTube/Vimeo video.

For ExpressionEngine 1 installation, pi.antenna.php should be added to /system/plugins/

For ExpressionEngine 2 installation, the directory /antenna should be placed in /system/expressionengine/third_party/

Usage
-------

	{exp:antenna url='{the_youtube_or_vimeo_url}' max_width="232" max_height="323"  wmode="transparent|opaque|window" iframe_class="class_name" iframe_id="id_name"}
	    {embed_code}
	    {video_title}
	    {video_author}
	    {video_author_url}
	    {video_thumbnail}

	    {if embed_code}
	        It worked! {embed_code}
	    {if:else}
	        No video to display here.
	    {/if}

	{/exp:antenna}


Set the `max_width` and/or `max_height` for whatever size your website requires. The video will be resized to be within those dimensions, and will stay at the correct proportions.

The optional `wmode` parameter can be used if you're experiencing issues positioning HTML content in front of the embedded media. It accepts values of transparent, opaque and window.

The `iframe_class` and `iframe_id` parameters will apply a class and/or id to your embed container if an iframe is returned.

If used as a single tag, it returns the HTML embed/object code for the video. If used as a pair, you get access to the 5 variables above and can use them in conditionals.

If you're using Vimeo, you get access to four more parameters:

- vimeo_byline='true/false' -- Shows the byline on the video. Defaults to true.
- vimeo_title='true/false' -- Shows the title on the video. Defaults to true.
- vimeo_autoplay='true/false' -- Automatically start playback of the video. Defaults to false.
- vimeo_portrait='true/false' -- Whether or not to display the video creator's avatar in the video poster frame. Defaults to true.
- vimeo_color="888888" -- A hexadecimal color code to be used as the Vimeo control accent color.

**NOTE** For this to work with all urls please ensure that in Weblog/Channel -> Preferences, you have 'Automatically turn URLs and email addresses into links?' set to 'No'. 

Compatibility
-------

**Antenna** is compatible with ExpressionEngine 1 & 2. The version for ExpressionEngine 1 has been tested on 1.6.9 but will likely work with older versions. The version for ExpressionEngine 2 has been tested on 2.1.

You must be using PHP 5.2+, though I haven't tested with PHP 5.3, and you must have the cURL library and PECL json installed.

Warranty/License
-------

There's no warranty of any kind. If you find a bug, please tell me and I may try to fix it. It's provided completely as-is; if something breaks, you lose data, or something else bad happens, the author(s) and owner(s) of this plugin are in no way responsible.

This plugin is owned by Matt Weinberg. You can modify it and use it for your own personal or commercial projects, but you can't redistribute it. EE2 and Vimeo functionality added by Adam Wiggall (@turnandface). Wmode compatibility added by Tom Davies (@metadaptive).
