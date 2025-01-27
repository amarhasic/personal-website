<script>
  // NATO phonetic alphabet mapping
  const natoAlphabet = {
    'A': 'Alpha', 'B': 'Bravo', 'C': 'Charlie', 'D': 'Delta',
    'E': 'Echo', 'F': 'Foxtrot', 'G': 'Golf', 'H': 'Hotel',
    'I': 'India', 'J': 'Juliet', 'K': 'Kilo', 'L': 'Lima',
    'M': 'Mike', 'N': 'November', 'O': 'Oscar', 'P': 'Papa',
    'Q': 'Quebec', 'R': 'Romeo', 'S': 'Sierra', 'T': 'Tango',
    'U': 'Uniform', 'V': 'Victor', 'W': 'Whiskey', 'X': 'X-ray',
    'Y': 'Yankee', 'Z': 'Zulu'
  };

  let currentLetter = '';
  let userAnswer = '';
  let feedback = '';
  let score = 0;
  let totalAttempts = 0;
  let showAnswer = false;
  let gameMode = 'waiting'; // waiting, playing, review

  function generateNewLetter() {
    const letters = Object.keys(natoAlphabet);
    currentLetter = letters[Math.floor(Math.random() * letters.length)];
    userAnswer = '';
    feedback = '';
    showAnswer = false;
  }

  function checkAnswer() {
    totalAttempts++;
    const correctAnswer = natoAlphabet[currentLetter];
    
    if (userAnswer.toLowerCase() === correctAnswer.toLowerCase()) {
      feedback = 'CORRECT';
      score++;
      setTimeout(generateNewLetter, 1500);
    } else {
      feedback = 'INCORRECT';
      showAnswer = true;
    }
  }

  function startGame() {
    score = 0;
    totalAttempts = 0;
    gameMode = 'playing';
    generateNewLetter();
  }

  function handleKeyPress(e) {
    if (e.key === 'Enter' && userAnswer && gameMode === 'playing') {
      checkAnswer();
    }
  }
</script>

<svelte:window on:keypress={handleKeyPress}/>

<div class="min-h-screen bg-gray-900 text-gray-100 p-8">
  <div class="max-w-3xl mx-auto">
    <!-- Header -->
    <div class="text-center mb-12">
      <h1 class="text-4xl font-bold text-green-500 mb-4 font-mono">NATO PHONETIC TRAINER</h1>
      <p class="text-gray-400 font-mono">MASTER THE NATO PHONETIC ALPHABET</p>
    </div>

    <!-- Main Content -->
    <div class="bg-gray-800 p-8 rounded-lg border-2 border-green-500 shadow-lg">
      {#if gameMode === 'waiting'}
        <!-- Start Screen -->
        <div class="text-center">
          <p class="mb-6 font-mono text-lg">PREPARE FOR TRAINING, OPERATOR</p>
          <button 
            on:click={startGame}
            class="bg-green-600 hover:bg-green-700 text-white font-bold py-3 px-6 rounded-md font-mono transition-colors"
          >
            INITIATE SEQUENCE
          </button>
        </div>
      {:else}
        <!-- Game Screen -->
        <div class="space-y-8">
          <!-- Score Display -->
          <div class="flex justify-between items-center font-mono text-sm">
            <div class="bg-gray-700 px-4 py-2 rounded">
              SCORE: {score}/{totalAttempts}
            </div>
            <div class="bg-gray-700 px-4 py-2 rounded">
              ACCURACY: {totalAttempts ? Math.round((score/totalAttempts) * 100) : 0}%
            </div>
          </div>

          <!-- Current Letter Display -->
          <div class="text-center">
            <div class="text-8xl font-bold mb-4 text-green-500">{currentLetter}</div>
            <input
              type="text"
              bind:value={userAnswer}
              placeholder="ENTER NATO PHONETIC CODE"
              class="w-full bg-gray-700 border-2 border-green-500 rounded-md py-3 px-4 text-center font-mono uppercase focus:outline-none focus:border-green-400"
              disabled={showAnswer}
            />
          </div>

          <!-- Feedback Area -->
          {#if feedback}
            <div class="text-center font-mono text-xl">
              <p class={feedback === 'CORRECT' ? 'text-green-500' : 'text-red-500'}>
                {feedback}
              </p>
              {#if showAnswer}
                <p class="text-gray-400 mt-2">
                  CORRECT CODE: {natoAlphabet[currentLetter]}
                </p>
              {/if}
            </div>
          {/if}

          <!-- Control Buttons -->
          <div class="flex justify-center space-x-4">
            <button
              on:click={checkAnswer}
              disabled={!userAnswer || showAnswer}
              class="bg-green-600 hover:bg-green-700 disabled:bg-gray-600 disabled:cursor-not-allowed text-white font-bold py-2 px-6 rounded font-mono transition-colors"
            >
              VERIFY
            </button>
            {#if showAnswer}
              <button
                on:click={generateNewLetter}
                class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-6 rounded font-mono transition-colors"
              >
                NEXT
              </button>
            {/if}
          </div>
        </div>
      {/if}
    </div>

    <!-- Reference Table -->
    <div class="mt-8 bg-gray-800 p-6 rounded-lg border-2 border-green-500">
      <h2 class="text-center font-mono text-xl mb-4 text-green-500">QUICK REFERENCE</h2>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 font-mono text-sm">
        {#each Object.entries(natoAlphabet) as [letter, word]}
          <div class="bg-gray-700 p-2 rounded text-center">
            <span class="text-green-500">{letter}</span> - {word}
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>