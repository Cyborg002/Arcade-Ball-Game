     ** js-arcade -classic-on-canvas **
	by Chris Deleon
	
	$Note: JavaScript is case sensitive so be careful with the pre defined functions and the functions you defined; 
	$Note: The 'var' (for variable)  can be of any type;
 
pt-2:  "Drawing and positions"
window.onload = function() { } //whatever you put inside that curly brace will load first

	Draw order is important; what comes last, overlapped the previous ones;
	In below example 'white' will overlapped the 'red';
	<!--Brief practice 	with 2d coordinates on canvas-->
		canvasContext.fillStyle = 'white';
		canvasContext.fillRect(350,250,100,100);  //box in center
		//Overlap and draw order in code
		canvasContext.fillStyle = 'red';
		canvasContext.fillRect(375,240,50,20);
	
pt-3:	"Movement and Time"
   #1 Create a function to group all Draw code; 
   #2 Calling a function multiple times;
   #3 Using a Variable to vary Shape Draw Position;
		try log("ballX") with quotes
   #4 Show Motion over Time (Basic Dynamic Animation);
		the ball is moved, but you can't see it because it is too fast;
		so you've to slow it down, to watch the action;
		setInterval(functionName, milliseconds);  for that much time it wait;
			$note: control the time, control the speed of animation. The smaller the number (in milliseconds) the smoother the animation;
   #5 Showing that the variable can be used as Any value;
		i.e. if you put ballX var instead of width it changes in width everytime;
		canvasContext.fillRect(25,240,ballX,20);
		or you can do these: canvasContext.fillRect(25,240,ballX,ballY);
				canvasContext.fillRect(ballX,240,ballX,20);
				canvasContext.fillRect(ballX,ballY,ballX,ballY);
				
pt-4:  "Clean Up the Code" (Mini)
	#1 Set update frequency as Frames Per Seconds;
	#2 Move and Resize the box (It'll become a paddle!);
	#3 Separate the Move Code from the Draw code;
	#4 Writing a function using the Inline Form; <<-- Important
		normal:
			function callBoth(){ moveShape();	drawShape();}
		Inline:
			setInterval(function(){ moveShape();	drawShape();}, 1000);
			
pt-5:  "Bouncing the ball"
	#1 Note about the code being all in the same file;
		not making the main HTML file bigger, make a separate file for js code;
	#2 Create a variable to support speed changes;
		var ballSpeedX;
	#3 Get the Ball moving in the Opposite direciton;
		negative number; var ballSpeedX= -2; //now it move to left;
	#4 Bounce the ball off the Right Canvas side;
	#5 Keep the ball's speed the same After Wall Bounce;
		ballSpeedX= -ballSpeedX;
	#6 Using Canvas dimensions instead of "Hard Coding";
		if(ballX > canvas.width-10);
	#7 Bounce the ball off the Left cnavas side too; 
		if(ballX < 10){ ballSpeedX= -ballSpeedX;}  //-ve x -ve = +ve
	#8 Creating functions for drawing the filled shapes;
		for optimizing the code;
		Change "canvasContext.fillRect()" with your function;
		function colorRect(leftX, topY, width, height, drawColor)
	#9 Use comments to document code purpose;
	
pt-6:  "Circle Draw Details" (mini)
	#1 Drawing the circle (making the ball round); 
		there is no circle function in HTML, and js;
		canvas.Context.arc(ballX, 100, 10, 0, math.PI* 2, true);
	#2 Break down of each line in filled circle draw;
		first two are X, and Y positions, but here it's the center of the circle;
		third is the radius of the circle;
	#3 Radiants for the start and end of the Drawn Arc;
		fourth is 'angle', fifth is 'Radiant', in js math.PI represents a half circle;
		last decides wheather it's clockwise, or counter-clockwise;
		if you set it to 'false' you can see the other section of the arc;
	#4 Dealing with Circle's Center, Radius, and color;
	#5 Create a function to draw any filled circle;
	
pt-7:  "Ball 2D motion, paddle"
	#1 Move and Bounce the ball vertically too;
		--add the Y-positions var;
	#2 Define Labeled values for paddle position and size;
		var paddle1Y= 250;		const PADDLE_HEIGHT= 100;
		ALL_CAPS convention  is from the #define in C programming;
		*note: it's just a convention, you can choose your own name;
	#3 Find the mouse position relative to game canvas;
		'evt' stands for event 
		return {x:mouseX, y:mouseY}; //technically this is one return value, It's just a js "Object Literal";
	#4 Set Paddle's position value whenever mouse moves;
	#5 Use Paddle's position var in the paddle's Draw Code;
	#6 Align the paddle's Center on the Mouse's Y position;
	
pt-8  "Ball Reset and collision"
	#1 Write a Function that can reset the ball;
	#2 Reset the ball when it reaches the left side;
	#3 Switch the ball's direciton each time it's scored;
	#4 Bounce the ball if it gets blocked by left paddle;
	#5 Draw a second paddle for the Right side;
	#6 Create a value label for paddle thickness;
	#7 Temporarily use mouse for testing right paddle;
	#8 Reset the ball if it goes past the right edge;
	#9 Give mouse control back to the left paddle; (For checking)
	
pt-9  "Paddle AI and scoring"
	#1 Get Right paddle chasing the ball's vertical position;
	#2 Style shift: From A=A+B to A+= B; just optimizing the code;
	#3 Test out how the Right paddle moves so far;
	#4 Line up Right paddle's center (!not Top) to ball;
	#5 Stop right paddle shake (sit still if close enough);
	#6 Put text on the screen to use for score display;
	#7 Set up, Update, and show score values on screen;
	
pt-10  "Ball control & Winning"
	#1 Brief Detour: Why Ball control matters;
	#1 Give Ball control based on where it hits the paddles;
	#2 Reset both scores when either team wins;
	#3 Turn off computer player to test scoring on right;
	#4 Stop the Game when either side wins;
	
pt-11  "Mouse click, Draw Net"
	#1 Restart upon mouse click when viewing End Screen;
	#2 Declare on the end screen which paddle side won;
	#3 Draw a Dashed Line Net Down the Play-field Center;	
	#4 How to continue learning this way;
	
	^^^^^^^^^^^^^^^**** THE_END ****^^^^^^^^^^^^^^^
	
===========================================================================================	
#### Problems:
#1. what's the code for trajectory along the Y-axis?

	
	
	
	
	
	
	
	
	
	
		