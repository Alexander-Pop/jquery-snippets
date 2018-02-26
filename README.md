# jquery-snippets

### Scroll to Top link
This small piece of code is used to navigate the user back to top of the page when they are at the bottom of the page.

  $(document).ready(function(){
    $("a.scrolltop").click(function() {
      $("html, body").animate({ scrollTop: 0 }, "slow");
      return false;
    });
  });
 

You need to create a html link with class  scrolltop . That’s it

### How to Reset / Clear the Form Values
This code will clear the form data after user submiting the form via ajax

$(document).ready(function(){
$('#formID')[0].reset();
});
 

formID  is the ID of the form.

### How to Prevent Users from Submitting the Form Twice
This below code will work perfect even on forms that have multiple submit buttons

$(document).ready(function(){
var $myForm = $("#formID");
$myForm.submit(function(){
$myForm.submit(function(){
return false;
});
});
});
 

### Zebra Table Design using jQuery
Zebra table is very famous and it is easy to differentiate alternate rows in a table. I hope this trick will improve the readability of the entire table. We need to write css code for class  .zebra  for background color

$(document).ready(function(){
$("table tr:even").addClass('zebra');
});

### How to Open Links in New Tab / Window
First link will open all the links in new tab where the second one will open in new tab if it has class  external 

$(document).ready(function(){
$( 'a[href^="http://"],a[href^="https://"]' ).attr( 'target','_blank' ); //open all links in new tab
$( 'a.external' ).attr( 'target','_blank' ); //links having external class only opens in new tab
});

### Check Value exists in an Array or Not using jQuery
jQuery has in-built function called inArray – Searches for a specified value within an array and return its index (or -1 if not found)

$(document).ready(function(){
var arr = [ 4, "Pete", 8, "John" ];
jQuery.inArray("value", arr);
// Usage
if( jQuery.inArray("4", arr) != -1 ) {
return true
};
});
 

### How to Get Client IP address using jQuery
ipinfo.io is FREE for 1000 requests a day. We can easily get more details about geo location from this API

$(document).ready(function () {
$.getJSON("http://jsonip.com/?callback=?", function (data) {
console.log(data);
alert(data.ip);
});
});
 

### Check If an Element is Hidden or Not?
This code is used to find the visibility of an element. Here element refers to html tag with selectors like .title, #heading etc

$(document).ready(function () {
$(element).is(":visible");
});
 

### How to Check If a Checkbox is Checked in jQuery?
By using jQuery’s is() function, we can achieve this functionality

$(document).ready(function () {
if($(element).is(':checked')) {
// checked
} else {
// unchecked
}
});

### How to Get the Size of the Window or the Document using jQuery?
If you are using jQuery, you can get the size of the window or the document using jQuery methods:

$(window).height(); // returns height of browser viewport
$(document).height(); // returns height of HTML document (same as pageHeight in screenshot)
$(window).width(); // returns width of browser viewport
$(document).width(); // returns width of HTML document (same as pageWidth in screenshot)
To get the screen size you have to use the  screen object 

screen.height;
screen.width;
 

### How to Check If an Element exists in jQuery
$(document).ready(function () {
if ($(element).length > 0)
{
alert("exists");
} else {
alert("doesn't exist");
}
});

### How to Count No of Rows in a Table
Below code is used to count the number of tr elements within the table. Check how to delete multiple rows from an table using jQuery

$(document).ready(function () {
var rowCount = $('#myTable tr').length;
});
 

### How to Prevent Right Click for Whole Page?
Below code will prevent right click in the whole document. Check how to prevent your content from copying using jQuery

$(document).ready(function () {
$(this).bind("contextmenu", function(e) {
e.preventDefault();
});
});

### How to Get Form Data using jQuery
Below code is used to get the form data both in string and arrays

$(document).ready(function () {
$('form').serialize() // returns a string
$('form').serializeArray() // returns an array
});

### How to Send a File and Form data in One Form using jQuery
You can upload data and files with one form using ajax. Create one php file and print the data to see the request.

$(document).ready(function () {
$("form").submit(function(e) {
e.preventDefault();
var formData = new FormData(this);
 
$.post($(this).attr("action"), formData, function(data) {
alert(data);
});
});
});
 

### How to access an element in the parent page from iFrame?
Below code is used to get the element data from an iFrame

$(document).ready(function () {
$('element', window.parent.document).html();
});
 

### How to Find the Length of the String using jQuery?
Below jquery code snippet is used to find the length the string

$(document).ready(function () {
$('#selector').val().length
$('.selector').val().length
});
Lowercase and Uppercase with jQuery
$(document).ready(function () {
$('#selector').val().toLowerCase();
$('#selector').val().toUpperCase();
});
 

### How to Check If an Element has a CSS Class with jQuery
This jquery code snippet is widely used among the web developers to  add or remove the class form an element after checking the class. This method will return TRUE or FALSE

  $(document).ready(function () {
    $("#selector").hasClass(className);
    $(".selector").hasClass(className);
  });
 

### How to Preview an Image Before it is Uploaded to Server?
It would be nice to display what is there in the image before uploaded to server. Cool feature right? Yeah

function readURL(input) {
 
if (input.files && input.files[0]) {
var reader = new FileReader();
 
reader.onload = function(e) {
$('#preview').attr('src', e.target.result);
}
 
reader.readAsDataURL(input.files[0]);
}
}
$(document).ready(function () {
$("#upload").change(function() {
readURL(this);
});
});
 
//html
<form id="form">
<input type='file' id="upload" />
<img id="preview" src="#" />
</form>
 
