==Selectors==
$() === queryselectorAll();

$(":input") -> select all input types

$("p:contains("hello")") --> select element or Text

$("div:has('.p')") -> select the parent element 

$("ul li:last") --> last first even odd

$("ul li:last").eq(3); -> select element by index;

--------------------------------------------------

$("p").attr("class") -> get
$("p").attr("class","hamada") -> set

-------------
==Style==

#("p").css("property", "vlaue");

#("p").css("
color : "red"
border: "1px solid"
");

==Classes==

#("p").addClass("class");
#("p").removeClass("class");
#("p").toggleClass("class");
$("p").hasClass("class");

==get==
$("#para").text();
$("#para").html();

==set==

$("#para").text("<p>ham  /p>");
$("#para").html("<p>ham  /p>");

==to ADD on the Html==

var oldVal = $("#para").html();
$("#para").html(oldVal + "<span>hallo <span>");


==val() get and set input value==
$("#para").val(); // get
$("#para").val("hello"); // set


==append append to==
$('#container').append("<p>hamad</p>");
$("<p>hamad</p>").appendTo("#container)

==prepend prepend to==

$('#container').prepend("<p>before<p>");
$("<p>hamad</p>").prependTo("#container)


==wrap==
$('#warp').wrap("<div></div>");
$("#wrap").wrap("<div class='div' ></div>");
$($('.container)[0]);

// remove , replace
$('#warp').remove();

== loops == 
$("#p").each(function(index, element){
})

------------------------------------- Events ----------------------------------
$("button").click(function (){
	console.log(this);
	$(this).css("color" , "red");
	 $(this).toggleClass("bgColor");
})

==// on -> bind(); deprecated==

// 4 cases

1. addEventListener

$("button").on("click. dbclick",function()
{
})

$("button").on("mouseenter  mouseleave",function()
{
	
})
// off

$("#stop").on("click",function(){
	// off
	$(".btn").off(); /// remove the listener
})
-------------------------------------------------------------------------------

// btn -> click -> click on Event

----------------------------------------------------
////////////////////////// chatgpt 
$("container").on("click", ".btn" , function()
{
	console.log('click');
})

$(.btn).on(
{
	mouseenter: function ()
	{
		console.log("mouse enter")
	}
	mouseover: function ()
	{
		console.log("mouse enter")
	}
})

-------------------------------------------------------------------

$("button").eq[0].click(function(){
	 $("div").hide();
	 $("div").show();
	 $("div").toggle();
});



