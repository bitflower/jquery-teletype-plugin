jQuery Teletype Plugin
======================

Teletype is a jQuery plugin that types out text, and then optionally deletes it, replicating human interaction.

Additional options provide the ability to preserve the typed text, in a console / terminal format, pause during typing and delete characters.

An online demo can be found at <http://teletype.rocks/>.

Installation
---

    <script src="jquery.js"></script>
	<script src="jquery.teletype.js"></script>
	<script>
		$( function() {
			$( '.type-text' ).teletype( {
				text: [ 'one', 'two', 'three' ],
				typeDelay: 0,
				backDelay: 20
			} );
		} );
	</script>
	...
	<div class="type-text"></div>

Options
-------

   
 Option     | Default     | Description
------------|-------------|------------
 text       | `['one','two','three']` (array) | List of strings to output.     
 typeDelay  | `100` (integer)                     | Minimum delay, in ms, between typing characters.    
 backDelay  | `50` (integer)                      | Minimum delay, in ms, between deleting characters.
 blinkSpeed | `1000` (integer)                    | Interval, in ms, that the cursor will flash.
 cursor     | <code>"&#124;"</code> (string)      | Character used to represent the cursor.
 delay      | `2000` (int)                        | Time in ms to pause before deleting the current text.
 preserve   | `false` (boolean)                   | Prevent auto delete of the current string and begin outputting the next string.
 prefix     | `""` (string)                       | Begin each string with this prefix value.
 loop       | `0` (int)                           | Number of times to loop through the output strings, for unlimited use `0`.
 humanise   | `true` (boolean)                    | Add a random delay before each character to represent human interaction.
 callbackNext | `""` (function)			  | Callback function that is called on every new word/text

Deleting characters `~`
---

It is possible to delete a defined number of characters then proceed with the rest of the text output. 

Use `~x ` within the text string, where x is an integer value defining the characters to backspace, followed by a space.

Example, type "auti", delete 1 character and continue to type "o", resulting in the word "auto":

```
auti~1 o^`
```

Pause / Delay `^`
---

Delay typing the next character using `^x ` where x in an integer value of milliseconds to pause.

To pause for 2 seconds after typing the word "pause" before continuing to type: 

```
pause^2000 more
```

Line Breaks `\n`
---

Line breaks can be added using `\n`, which are converted to `<br />` during output.

Generated Markup
---

The following markup is used to output the teletype text.

```
<span class="teletype-prefix">[prefix]</span>
<span class="teletype-text">[string]</span>
<span class="teletype-cursor">[cursor]</span>
```
    
This provides the ability to customise the style of the output text in your CSS.

Minification
---

The Minified version of this script was provided by UglifyJS 2 - an online version can be found at <http://gpbmike.github.io/refresh-sf/>.
