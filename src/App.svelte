<script>
  let q1 = ''
  let q2 = ''
  let q3 = ''
  let q4 = ''
  let q5 = ''
  let currentscore = ''
  let count = 0
  let answers = ['', '', '', '', '']
  let i = 0
  let qnum = 1
  let finalscore = ''

  function check(ans){
    if (qnum === 1) {
      document.getElementById("button1").style.display = "none";
    } else if (qnum === 2) {
      document.getElementById("button2").style.display = "none";
    } else if (qnum === 3) {
      document.getElementById("button3").style.display = "none";
    }
    qnum++

    i++
    while (i < 4) {
      let text = ''
      if (ans === 'true' || ans === 'carex secta'){
        count+= 1 
        text = 'correct!'
      } else {
        text = 'false!'
      }
      text += ' current score is ' + count
      answers[i-1] = text

      if (qnum === 4) {
        finalscore = 'Your final score is ' + count
      }
      return answers
    }
    
  }

  function reset() {
    q1 = ''
    q2 = ''
    q3 = ''
    q4 = ''
    q5 = ''
    currentscore = ''
    count = 0
    answers = ['', '', '', '', '']
    i = 0
    qnum = 1
    finalscore = ''
    document.getElementById("button1").style.display = "block"
    document.getElementById("button2").style.display = "block"
    document.getElementById("button3").style.display = "block"
  }

</script>

<h3>Native Plants Quiz</h3>
<p>Identifing Native Plants</p>

<br>
<p>conifer (cone bearing) tree, can grow over 50m</p>
<label>
	<input type=radio bind:group={q1} value={'a'}>
	kowhai
</label>

<label>
	<input type=radio bind:group={q1} value={'b'}>
	poroporo
</label>

<label>
	<input type=radio bind:group={q1} value={'true'}>
	kahikatea
</label>

<label>
	<input type=radio bind:group={q1} value={'c'}>
	cabbage tree
</label>

<button id='button1' on:click={check(q1)}>
  Check
</button>

<p>{answers[0]}</p>

<br>
<p>tussock forming sedge, 1.5-7mm wide light green/yellow-green leaves, up to 1.5m</p>

<label>
	<input type=text value={q2}>
	
</label>

<button id='button2' on:click={check(q2)}>
  Check
</button>

<p>{answers[1]}</p>

<br><br>
<p>Which of these are trees</p>

<label>
	<input type=checkbox bind:group={q3} value={'true'}>
	kowhai
</label>

<label>
	<input type=checkbox bind:group={q3} value={'h'}>
	mahoe
</label>

<label>
	<input type=checkbox bind:group={q3} value={'i'}>
	lancewood
</label>

<label>
	<input type=checkbox bind:group={q3} value={'j'}>
	karamu
</label>

<button id='button3' on:click={check(q3)}>
  Check
</button>

<p>{answers[2]}</p>
