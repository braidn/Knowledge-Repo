##Notes

* Much like haml in that it is white space dependent
* When building yield content make sure to call `extends layoutName`
	* This goes along with Node's explicit nature

###Block Content

* Specific areas that are defined in a layout file
* Any file being rendered into that file can wrap content in the same name
this will lead to content being rendered exactly where you want it
