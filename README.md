backbone.controller
===================

Controller "à la Playframework" for Backbone.js

##Install it

	<script src="backbone.controller.js"></script>

##Create a controller

It's like Playframework!> v°1 Controllers. I use static members :

	var myControllerOfSomething = Backbone.Controller.extend({},{

		doSomeThing : function () {
			//...
		},

		CallMeWithParameters : function (params) {
			//...
		},

		displaySomeThing : function () {
			aBackboneView.render();
		},

		doAll : function() {
			myControllerOfSomething.doSomeThing();
			myControllerOfSomething.CallMeWithParameters("hello");
			myControllerOfSomething.displaySomeThing();
		}
	});

##Use it

	window.RoutesManager = Backbone.Router.extend({
		routes : {
			
			"call/:param" : "callWithParam",
			"do" : "do"
			"*path" : "root"
		},

		root : function () { 
			myControllerOfSomething.doAll();
		},

		do : function () {
			myControllerOfSomething.doSomeThing();
		},

		display : function () { 
			myControllerOfSomething.displaySomeThing(); 
		},

		callWithParam : function (param) {
			myControllerOfSomething.CallMeWithParameters(params);
		}

	});
