function srcGameZone(){

    let gamesSection1 = document.querySelector("body > section.games1");
    let gamesSection2 = document.querySelector("body > section.games2");
    let tictactoeBtn = document.querySelector("#tictactoeBtn");
    let memoryGameBtn = document.querySelector("#memoryGameBtn");
    let numPuzzleGameBtn = document.querySelector("#numPuzzleGameBtn");
    let guessTheFlagBtn = document.querySelector("#guessTheFlagBtn");
    let fastTypingBtn = document.querySelector("#fastTypingBtn");
    let homePageBtn = document.querySelectorAll('.homePageBtn');

    homePageBtn.forEach(btn => {
        btn.addEventListener('click', function goToHomePage(){
            location.reload();
        });
    });

    /* --- Tic Tac Toe --- */
    tictactoeBtn.addEventListener('click', function tictactoeStart(){
    document.querySelector("body > section.title").innerHTML='';
    gamesSection1.style.display= 'none';
    gamesSection2.style.display= 'none';


    document.querySelector("body > section.tictactoeSection").style.display = 'inline';

    const boxes = Array.from(document.querySelectorAll('.box'));
    const displayPlayer = document.querySelector('.display-player');
    const resetBtn = document.querySelector("body > section.tictactoeSection > section.res > button");
    const winnerDisplay = document.querySelector('.winner');

    let board = ['', '', '', '', '', '', '', '', ''];
    let currPlayer = 'X';
    let isGameActive = true;

    const PLAYERX_WON = 'PLAYERX_WON';
    const PLAYERO_WON = 'PLAYERO_WON';
    const TIE = 'TIE';

    const winningConditions = [
            [0, 1, 2],
            [3, 4, 5],
            [6, 7, 8],
            [0, 3, 6],
            [1, 4, 7],
            [2, 5, 8],
            [0, 4, 8],
            [2, 4, 6]
    ];

    function handleResultValidation() {
        let roundWon = false;
        for (let i = 0; i <= 7; i++) { // [0;7] winning conditions
            const winCondition = winningConditions[i]; // curr win condition (from 0 to 7)
            const a = board[winCondition[0]]; // first line of board
            const b = board[winCondition[1]]; // second line of board
            const c = board[winCondition[2]]; // third line of board

            if (a === '' || b === '' || c === '') { // if they're empty
                continue;
            }

            if (a === b && b === c) { // if they match
                roundWon = true;
                break;
            }

        }

    if (roundWon) { // if someone win
            announceWinner(currPlayer === 'X' ? PLAYERX_WON : PLAYERO_WON); // check who win
            isGameActive = false; // game over
            return;
        }

    if (!board.includes(''))
        announceWinner(TIE);
    }

    const announceWinner = (who) => {
        switch(who){
            case PLAYERO_WON:
                winnerDisplay.innerHTML = '<span class="playerO">O</span> Won';
                alert('Game Over!');
                break;
            case PLAYERX_WON:
                winnerDisplay.innerHTML = '<span class="playerX">X</span> Won';
                alert('Game Over!');
                break;
            case TIE:
                winnerDisplay.innerText = 'Tie';
                alert('Game Over!');
        }
        winnerDisplay.classList.remove('hide');
    };

    const isValidAction = (box) => {
        if (box.innerText === 'X' || box.innerText === 'O'){
            return false;
        }

        return true;
    };

    const updateBoard =  (index) => {
        board[index] = currPlayer; 
    }

    const changePlayer = () => {
        displayPlayer.classList.remove(`player${currPlayer}`);
        currPlayer = currPlayer === 'X' ? 'O' : 'X';
        displayPlayer.innerText = currPlayer;
        displayPlayer.classList.add(`player${currPlayer}`);
    }

    const userAction = (box, index) => {
        if(isValidAction(box) && isGameActive) {
            box.innerText = currPlayer;
            box.classList.add(`player${currPlayer}`);
            updateBoard(index);
            handleResultValidation();
            changePlayer();
        }
    }
    
    const resetBoard = () => {
        board = ['', '', '', '', '', '', '', '', ''];
        isGameActive = true;
        winnerDisplay.classList.add('hide');

        if (currPlayer === 'O') {
            changePlayer();
        }

        boxes.forEach(box => {
            box.innerText = '';
            box.classList.remove('playerX');
            box.classList.remove('playerO');
        });
    }

    boxes.forEach( (box, index) => {
        box.addEventListener('click', () => userAction(box, index));
    });

    resetBtn.addEventListener('click', resetBoard);

});

    /* --- Memory Game --- */
    memoryGameBtn.addEventListener('click', function memoryGameStart(){
        document.querySelector("body > section.title").innerHTML='';
        document.querySelector("body > section.title").innerHTML='Memory Game';
        document.querySelector("body > section.title").style.margin = '6%';
        document.querySelector("body > section.title").style.fontSize = '55px'; 
        gamesSection1.style.display= 'none';
        gamesSection2.style.display= 'none';

        document.querySelector("body > section.memoryGameSection").style.display = 'block';

        cardArray=[
            {text: "A", image: "img1.png"},
            {text: "A", image: "img1.png"},
            {text: "B", image: "img2.png"},
            {text: "B", image: "img2.png"},
            {text: "C", image: "img3.png"},
            {text: "C", image: "img3.png"},
            {text: "D", image: "img4.png"},
            {text: "D", image: "img4.png"},
            {text: "E", image: "img5.png"},
            {text: "E", image: "img5.png"},
            {text: "F", image: "img6.png"},
            {text: "F", image: "img6.png"}
          ];
          
          clickedCard=[];
          matchedCard=[];
          let countMatch = 0;
          
          let shuffleDeck=function(){
          
          let currentIndex = 
          cardArray.length
          , temporaryValue
          , randomIndex;

          
          
          while (0 !== currentIndex) {
            
            randomIndex = Math.floor(Math.random() * currentIndex);
            currentIndex -= 1;
          
            
            temporaryValue = cardArray[currentIndex];
            cardArray[currentIndex] = cardArray[randomIndex];
            cardArray[randomIndex] = temporaryValue;
          }
          }
          
          shuffleDeck();
          var board=document.getElementById("boardMG");
          
          for(var i=0; i<cardArray.length; i++){
          
          
          var cardsBack=document.createElement("div");
          cardsBack.classList.add("cardMG");
          board.appendChild(cardsBack);
          
          
          var images=document.createElement("img");
          images.src = cardArray[i].image;
          images.className="image";
          cardsBack.appendChild(images);
          
          
          cardsBack.addEventListener("click",function(){
            var card = this;
            if (clickedCard.length < 2){
             card.classList.add("image");
              card.classList.add("match"); 
              clickedCard.push(card.innerHTML);
              matchedCard.push(card);
              
              if (clickedCard.length === 2){
                if (clickedCard[0] === clickedCard[1]){
          
                    clickedCard=[];
                    matchedCard=[];
                    countMatch++;
                    document.getElementById('counter').innerHTML=countMatch.toString();

                    if(countMatch == 6){
                        document.getElementById('winsMG').innerHTML='Well done!You matched all the cards!';
                        document.getElementById('winsMG').style.color = '#fff';
                        document.getElementById('winsMG').style.textAlign = 'center';
                    }
                } else {
                  
                  setTimeout(turnOffAllCards, 1000);
                  for (i=0; i<matchedCard.length; i++){
                    matchedCard[i].classList.remove("match");
                  }
                  matchedCard=[];
                   
                }
              } 
            } 
            
          });
          } 
          
          function turnOffAllCards(){
          var frontCards = document.querySelectorAll("div.image:not(.match)");
          for(var i = 0; i < frontCards.length; i++){
            frontCards[i].classList.remove("image");
            clickedCard=[];
          
          }
          
          }
    });

    /* --- Number Puzzle Game --- */
    numPuzzleGameBtn.addEventListener('click', function numPuzzleGameStart(){
        document.querySelector("body > section.title").innerHTML='';
        document.querySelector("body > section.title").innerHTML='Number Puzzle';
        document.querySelector("body > section.title").style.margin = '6%';
        document.querySelector("body > section.title").style.fontSize = '55px'; 
        gamesSection1.style.display= 'none';
        gamesSection2.style.display= 'none';

        document.querySelector("body > section.numPuzzleSection").style.display = 'flex';
        document.querySelector("body > section.numPuzzleSection").style.justifyContent = "center"; 
        document.querySelector("body > section.numPuzzleSection").style.alignItems= "center";
        document.querySelector("body > section.numPuzzleSection").style.flexDirection = "column"; 

        class Box {

            constructor(x, y) {
              this.x = x;
              this.y = y;
            }
          
            getTopBox() { //the top is in position 0(first) relative to the axis y 
              if (this.y === 0) return null;
              return new Box(this.x, this.y - 1);
            }
        
            getBottomBox() { ////the bottom is in position 3(last) relative to the axis y 
                if (this.y === 3) return null;
                return new Box(this.x, this.y + 1);
              }
          
            getRightBox() { //the right is in position 3(last) relative to the axis x
              if (this.x === 3) return null;
              return new Box(this.x + 1, this.y);
            }
          
            getLeftBox() { //the left is in position 0(first) relative to the axis x
              if (this.x === 0) return null;
              return new Box(this.x - 1, this.y);
            }
          
            getPossibleBoxes() { 
              return [
                this.getTopBox(),
                this.getRightBox(),
                this.getBottomBox(),
                this.getLeftBox() ]
            .filter(box => box !== null);
        }
          
            getRandomGenerator() {
              const nextdoorBoxes = this.getPossibleBoxes();
              return nextdoorBoxes[Math.floor(Math.random() * nextdoorBoxes.length)];
            }
        }  
          
        
        
        
          const swap = (grid, box1, box2) => {
            const temp = grid[box1.y][box1.x];
            grid[box1.y][box1.x] = grid[box2.y][box2.x];
            grid[box2.y][box2.x] = temp;
          };
          
          const isSolved = grid => {
            return (
              grid[0][0] === 1 &&
              grid[0][1] === 2 &&
              grid[0][2] === 3 &&
              grid[0][3] === 4 &&
              grid[1][0] === 5 &&
              grid[1][1] === 6 &&
              grid[1][2] === 7 &&
              grid[1][3] === 8 &&
              grid[2][0] === 9 &&
              grid[2][1] === 10 &&
              grid[2][2] === 11 &&
              grid[2][3] === 12 &&
              grid[3][0] === 13 &&
              grid[3][1] === 14 &&
              grid[3][2] === 15 &&
              grid[3][3] === 0
            );
          };
          
          const getRandomGrid = () => {
            let grid = [[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12], [13, 14, 15, 0]];
          
            // Shuffle boxes
            let blankBox = new Box(3, 3);
            for (let i = 0; i < 1000; i++) {
              const randomNextdoorBox = blankBox.getRandomGenerator();
              swap(grid, blankBox, randomNextdoorBox);
              blankBox = randomNextdoorBox;
            }
          
            if (isSolved(grid)) return getRandomGrid();
            return grid;
          };
          
          class State {
            constructor(grid, move, time, status) {
              this.grid = grid;
              this.move = move;
              this.time = time;
              this.status = status;
            }
          
            static ready() {
              return new State(
                [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]],
                0,
                0,
                "ready"
              );
            }
          
            static start() {
              return new State(getRandomGrid(), 0, 0, "playing");
            }
          }
          
          class Game {
            constructor(state) {
              this.state = state;
              this.tickId = null;
              this.tick = this.tick.bind(this);
              this.render();
              this.handleClickBox = this.handleClickBox.bind(this);
            }
          
            static ready() {
              return new Game(State.ready());
            }
          
            tick() {
              this.setState({ time: this.state.time + 1 });
            }
          
            setState(newState) {
              this.state = { ...this.state, ...newState };
              this.render();
            }
          
            handleClickBox(box) {
              return function() {
                const nextdoorBoxes = box.getPossibleBoxes();
                const blankBox = nextdoorBoxes.find(
                  nextdoorBox => this.state.grid[nextdoorBox.y][nextdoorBox.x] === 0
                );
                if (blankBox) {
                  const newGrid = [...this.state.grid];
                  swap(newGrid, box, blankBox);
                  if (isSolved(newGrid)) {
                    clearInterval(this.tickId);
                    this.setState({
                      status: "won",
                      grid: newGrid,
                      move: this.state.move + 1
                    });
                  } else {
                    this.setState({
                      grid: newGrid,
                      move: this.state.move + 1
                    });
                  }
                }
              }.bind(this);
            }
          
            render() {
              const { grid, move, time, status } = this.state;
          
              // Render grid
              const newGrid = document.createElement("div");
              newGrid.className = "grid";
              for (let i = 0; i < 4; i++) {
                for (let j = 0; j < 4; j++) {
                  const button = document.createElement("button");
          
                  if (status === "playing") {
                    button.addEventListener("click", this.handleClickBox(new Box(j, i)));
                  }
          
                  button.textContent = grid[i][j] === 0 ? "" : grid[i][j].toString();
                  newGrid.appendChild(button);
                }
              }
              document.querySelector(".grid").replaceWith(newGrid);
          
              // Render button
              const newButton = document.createElement("button");
              if (status === "ready") newButton.textContent = "Play";
              if (status === "playing") newButton.textContent = "Reset";
              if (status === "won") newButton.textContent = "Play";
              newButton.addEventListener("click", () => {
                clearInterval(this.tickId);
                this.tickId = setInterval(this.tick, 1000);
                this.setState(State.start());
              });
              document.querySelector("body > section.numPuzzleSection > button").replaceWith(newButton);
          
              // Render move
              document.getElementById("move").textContent = `Move: ${move}`;
          
              // Render time
              document.getElementById("time").textContent = `Time: ${time}`;
          
              // Render message
              if (status === "won") {
                document.querySelector(".message").textContent = "You win!";
              } else {
                document.querySelector(".message").textContent = "";
              }
            }
          }
          
          const GAME = Game.ready();
          
    });

    /* --- Guess The Flag Game --- */
    guessTheFlagBtn.addEventListener('click', function guessTheFlagStart(){
        document.querySelector("body > section.title").innerHTML='';
        document.querySelector("body > section.title").innerHTML='Guess the flag!';
        gamesSection1.style.display= 'none';
        gamesSection2.style.display= 'none';
    
    
        document.querySelector("body > section.guessTheFlagSection").style.display = 'inline';
    
        let correctAnswers = [
            "Germany", 
            "Italy", 
            "Austria", 
            "Serbia", 
            "United States",
            "Argentina", 
            "Russia", 
            "India",
            "Monaco",
            "Ireland",
            "Libya",
            "Cyprus",
            "Turkey",
            "Romania",
            "Thailand",
            "Portugal",
            "Canada",
            "Colombia",
            "China",
            "Peru"
          ];
        
            let numRightAnsw = 0;
            let index = 0;
          
            const buttons = Array.from(document.querySelectorAll(".answer-text"));
          
            for (let button of buttons) {
          
              button.addEventListener('click', nextQuestion);
          
              function nextQuestion(event) {
          
                if (correctAnswers.includes(button.textContent)) {
                  numRightAnsw++
                }
          
                let currentSection = document.querySelectorAll('#sectionF')[index];  
                currentSection.style.display = 'none'; 
          
                if (document.querySelectorAll('#sectionF')[index + 1] !== undefined) { 
                  let nextSection = document.querySelectorAll('#sectionF')[index + 1];
                  nextSection.style.display = 'block'; 
                  index++; 
                } else {
                  const results = document.querySelector('#results'); 
                  results.style.display = "block"; 
          
                  if (numRightAnsw < 20 && numRightAnsw != 1 && numRightAnsw != 0) {
                    document.querySelector("#results h1").textContent = `You got ${numRightAnsw} / 20 correct answers.`; 
                  }else if(numRightAnsw == 1){
                    document.querySelector("#results h1").textContent = 'You have only one correct answer! ';
                  }else if(numRightAnsw == 0){
                    document.querySelector("#results h1").textContent = 'You have no correct answer! 😔';
                  } else {
                    document.querySelector("#results h1").textContent = "Well done! You know the flags!";
                  }
                   
          
                }
          
              }
          
            }

    });

    /* --- Fast Typing Game --- */
    fastTypingBtn.addEventListener('click', function fastTypingStart(){
    document.querySelector("body > section.title").innerHTML='';
    gamesSection1.style.display= 'none';
    gamesSection2.style.display= 'none';
    
    document.querySelector("body > section.fastTypingSection").style.display = 'inline';

    let startBtnFT = document.querySelector("body > section.fastTypingSection > div > button");

    startBtnFT.addEventListener('click', init);

    const currentLevel = 5;
    
    let time = currentLevel;
    let score = 0;
    let isPlaying;
    
    const wordInput = document.querySelector('#word-input');
    const currentWord = document.querySelector('#current-word');
    const scoreDisplay = document.querySelector('#score');
    const timeDisplay = document.querySelector('#timeFT');
    const message = document.querySelector('#message');
    const seconds = document.querySelector('#seconds');
    const highscoreDisplay = document.querySelector('#highscore');
    
    const words = [
      'cold',
      'intelligent',
      'lucky',
      'depend',
      'agreement',
      'relationship',
      'campaign',
      'runaway',
      'case',
      'different',
      'establishment',
      'opportunity',
      'employee',
      'husband',
      'pattern',
      'history',
      'siblings',
      'investigate',
      'quickly',
      'information',
      'laughter',
      'newspaper',
      'health',
      'forward',
      'government',
      'sometimes',
      'trouble',
      'understand',
      'weapon',
      'wonder',
      'young'
    ];
    
    
    function init() {
      
      seconds.innerHTML = currentLevel;
      
      showWord(words);
      
      wordInput.addEventListener('input', startMatch);
      
      setInterval(countdown, 1000);
      
      setInterval(checkStatus, 50);
    }
    
    
    function startMatch() {
      if (matchWords()) {
        isPlaying = true;
        time = currentLevel + 1;
        showWord(words);
        wordInput.value = '';
        score++;
      }
      
      
      if (typeof sessionStorage['highscore'] === 'undefined' || score > sessionStorage['highscore']) {
        sessionStorage['highscore'] = score;
      } else {
        sessionStorage['highscore'] = sessionStorage['highscore'];
      }
    
      
      if (sessionStorage['highscore'] >= 0) {
      highscoreDisplay.innerHTML = sessionStorage['highscore'];
      }
    
      
      if (score === -1) {
        scoreDisplay.innerHTML = 0;
      } else {
        scoreDisplay.innerHTML = score;
      }
    }
    
    
    function matchWords() {
      if (wordInput.value === currentWord.innerHTML) {
        message.innerHTML = 'Correct!';
        return true;
      } else {
        message.innerHTML = '';
        return false;
      }
    }
    
    
    function showWord(words) {
      
      const randIndex = Math.floor(Math.random() * words.length);
      
      currentWord.innerHTML = words[randIndex];
    }
    
    
    function countdown() {
      
      if (time > 0) {
        
        time--;
      } else if (time === 0) {
        
        isPlaying = false;
      }
      
      timeDisplay.innerHTML = time;
    }
    
    
    function checkStatus() {
      if (!isPlaying && time === 0) {
        message.innerHTML = 'Game Over!';
        score = -1;
      }
    }
    });
}


