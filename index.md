<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>KUIS HJ</title>
	<style type="text/css">
		body{
			background-image: url(masjid.jpeg);
			background-size: 100% 100%;
			background-repeat: no-repeat;
			background-attachment: fixed;
		}
		#awal{
			position:absolute;
			left: 50%;
    		top: 50%;
			transform: translate(-50%,-50%);
   	 		padding: 20px 25px;
    		width: 500px;
			background-color: rgba(56, 54, 54, 0.8);
  		  	box-shadow: 0 0 10px rgba(39, 37, 37, 0.842);
		}
		#opening h1{
			text-align: center;
			font-family: Arial;
			font-size: 49px;
			font-weight: bold;
			position: relative;
			bottom:15px;
			color:white;
			text-shadow: 5px 3px 1px rgba(212, 129, 34,0.5);
		}
		#opening button{
			box-sizing: border-box;
  			-webkit-appearance: none;
    		-moz-appearance: none;
         	appearance: none;
 			background-color: rgb(33, 44, 44);
			box-shadow: 0 0 15px white;
			border-radius: 0.6em;
			color:white;
			cursor: pointer;
			display: flex;
			align-self: center;
			font-size: 1rem;
			font-weight: 400;
			line-height: 1;
			margin:auto;
			padding:2em 3em;
			text-decoration: none;
			text-align: center;
			text-transform: uppercase;
			font-family: 'Montserrat', sans-serif;
			font-weight: 700;
		}
		#opening button:hover{
			box-shadow: 0 0.5em 0.5em -0.4em var(--hover);
  			transform: translateY(-0.25em);
		}
		#isi{
			position:absolute;
			left: 50%;
    		top: 50%;
			transform: translate(-50%,-50%);
   	 		padding: 20px 25px;
    		width: 500px;
			background-color: rgb(3, 3, 3,0.8);
  		  	box-shadow: 0 0 10px rgba(39, 37, 37, 0.842);
			color:white;
		}
		#isi button{
			box-sizing: border-box;
  			-webkit-appearance: none;
    		-moz-appearance: none;
         	appearance: none;
 			background-color: rgb(33, 44, 44);
			border-radius: 0.6em;
			width: 100%;
			color:white;
			cursor: pointer;
			display: flex;
			font-size: 19px;
			font-weight: 400;
			line-height: 1;
			padding: 5px;
			margin-top:30px;
			text-decoration: none;
			text-transform: uppercase;
			font-family: 'Montserrat', sans-serif;
			font-weight: 700;
		}
		#isi button:hover{
			box-shadow: 0 0.5em 0.5em -0.4em var(--hover);
  			transform: translateY(-0.25em);

		}
		#isi button p{
			position: relative;
			left:215px;
		}
		#isi ul li{
			list-style:none;
			padding: 10px;
			margin-left:100px;
			position: relative;
			right:65px;
		}
		#question{
		 margin-left:70px;
		}
		#penutup{
			position:absolute;
			left: 50%;
    		top: 50%;
			transform: translate(-50%,-50%);
   	 		padding: 20px 25px;
    		width: 500px;
			background-color: rgba(56, 54, 54, 0.8);
  		  	box-shadow: 0 0 10px rgba(39, 37, 37, 0.842);
		}
		#penutup h1{
			text-align: center;
			font-family: Arial;
			font-size: 49px;
			font-weight: bold;
			position: relative;
			bottom:15px;
			color:white;
			text-shadow: 5px 3px 1px rgba(212, 129, 34,0.5);
		}
		#penutup button{
			box-sizing: border-box;
  			-webkit-appearance: none;
    		-moz-appearance: none;
         	appearance: none;
 			background-color: rgb(33, 44, 44);
			border-radius: 0.6em;
			width: 200px;
			color:white;
			cursor: pointer;
			display: flex;
			font-size: 19px;
			font-weight: 400;
			line-height: 1;
			padding: 10px;
			position: relative;
			left:150px;
			margin-top:30px;
			text-decoration: none;
			text-transform: uppercase;
			font-family: 'Montserrat', sans-serif;
			font-weight: 700;
		}
		#penutup button a{
			text-decoration: none;
			color:white;
			position: relative;
			left:30px;
		}
		#penutup button:hover{
			box-shadow: 0 0.5em 0.5em -0.4em var(--hover);
  			transform: translateY(-0.25em);
		}
		.hidden {
			display: none;
		}
@media screen and (min-width:360px){
	body{
		width: 500px;
	}
	#opening h1{
			font-size: 30px;
			font-weight: bold;
		}

}

	</style>
</head>
<body>
	<div id="awal">
		<div id="opening">
		<h1>Selamat Datang di Quiz HJ</h1>
		<button onclick="startQuiz()">Play Quiz</button>
		</div>
	</div>

	<div id="isi" class="hidden">
<div id="quiz_window">
	<h1 id="question"></h1>
<ul>
	<li><input type="radio" name="choices" data-id="0" id="choice0">
	<label for="choice0" id="choiceText0"></label>
	</li>
	<li><input type="radio" name="choices" data-id="1" id="choice1">
	<label for="choice1" id="choiceText1"></label>
	</li>
	<li><input type="radio" name="choices" data-id="2" id="choice2">
	<label for="choice2" id="choiceText2"></label>
	</li>
</ul>

<button onclick="nextQuestion()"><p>Next</p></button>
</div>
</div>
	<div id="penutup" class="hidden">
<div id="closing_window">
	<h1>Quiz Selesai</h1>
	<button><a href="https://karpetmasjid.co.id/">Claim Now</a></button>
</div>
	</div>
<!-- //========================
=========Data===========
======================== -->
<script>
	const DB_QUIZ = [
	{
			question: "Apakah Bumi Itu Bulat?",
			answers:['Iya, bulat','Tidak, datar','Saya tidak perduli']
	},
	{

		 		question: "Berapa 1+1x5x0?",
			answers:['5', '0', '1'] 
	},
	{

			question: "Berapa 5 + 3?",
			answers:['9', '8', '7'],
	}
	]

	const CORRECT_ANSWER = [0, 2, 1]

	function startQuiz() {
		document.getElementById('awal').style.display = "none"
		document.getElementById('isi').style.display = "block"
	}

	let current_q = 0
	let total_score = 0
	let saved_answer = []

	document.addEventListener("DOMContentLoaded", function(event) {
		setupQuestion()
	});


	function setupQuestion() {
		document.getElementById('question').innerText = DB_QUIZ[current_q]['question']
		document.getElementById('choiceText0').innerText = DB_QUIZ[current_q]['answers'][0]
		document.getElementById('choiceText1').innerText = DB_QUIZ[current_q]['answers'][1]
		document.getElementById('choiceText2').innerText = DB_QUIZ[current_q]['answers'][2]
	}

	function nextQuestion() {
		current_q++

		saveAnswer()

		if (current_q > DB_QUIZ.length - 1)

			stopQuiz()

		resetState()
		setupQuestion()

	}

		function resetState() {
			const choosedAnswer = document.querySelector('input[name="choices"]:checked')
				if(choosedAnswer != null)
				choosedAnswer.checked = false
		}

		function stopQuiz() {
			checkScore()
			
		document.getElementById('isi').style.display = "none"
		document.getElementById('penutup').style.display = "block"
		return
		}

		function saveAnswer() {
			const answer = document.querySelector('input[name="choices"]:checked');
			if (answer != null) {
				saved_answer.push(parseInt(answer.getAttribute('data-id')))
				
			} else {
				saved_answer.push(0)
			}
		}

		function checkScore() {
			for (i = 0; i < saved_answer.length; i++){
				if (saved_answer[i] == CORRECT_ANSWER[i])
				total_score += 100
			}
		}
</script>
</body>
</html>
