<script>
    import "/src/app.css";
  
    export let title = "Europa contemporană: Unitate, diversitate, integrare";
  
    export let sections = [
      {
        content: "Europa contemporană: Unitate, diversitate, integrare. Ideea unei Europe unite a existat încă din antichitate, manifestându-se prin Imperiul Roman, creștinism și imperiile medievale.",
        imageUrl: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRl5-ijBc1R_S14d5AyRPxL8CIcAeRH6R9HQw&s",
        imageAlt: "Imagine reprezentând Europa contemporană"
      },
      {
        content: "Istoria unității europene: Imperiul Roman a creat o unitate europeană prin răspândirea limbii latine și a dreptului roman, contribuind la formarea unei baze comune în Europa.",
        imageUrl: "https://cdn.kastatic.org/ka-perseus-images/9330b8ab44e4a9039a30b4d50dc8072bab4698bf.png",
        imageAlt: "Ilustrație a Imperiului Roman"
      },
      {
        content: "Unitatea culturală a Europei: Creștinismul a jucat un rol esențial în unificarea culturală a continentului, iar imperiile medievale au urmărit realizarea unei unități politice.",
        imageUrl: "https://ziarullumina.ro/thumbs/landscape_big/2009/06/20/crestinismul-a-schimbat-modul-in-care-poate-fi-privita-istoria-94556.jpg",
        imageAlt: "Simboluri creștine și medievale"
      },
      {
        content: "Gânditori europeni: Încă din evul mediu, gânditori precum Victor Hugo (1849) au visat la o Europă unitară, exprimată prin sintagma “Statele unite ale Europei”.",
        imageUrl: "https://www.rador.ro/wp-content/uploads/2019/02/victor-hugo.jpg",
        imageAlt: "Portret stilizat al lui Victor Hugo"
      },
      {
        content: "Cauzele creării Uniunii Europene: Cele două războaie mondiale și apariția comunismului au evidențiat necesitatea unirii europene pentru a preveni conflictele viitoare.",
        imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/20/WWImontage.jpg/220px-WWImontage.jpg",
        imageAlt: "Ilustrație reprezentativă pentru războaiele mondiale"
      },
      {
        content: "Obiectivele creării Uniunii Europene: Unificarea industriei cărbunelui și oțelului pentru a rezolva conflictul Franco-German și a opri expansiunea comunismului a fost esențială pentru refacerea economică a Europei.",
        imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b8/European_Coal_and_Steel_Community_Map_1952.svg/300px-European_Coal_and_Steel_Community_Map_1952.svg.png",
        imageAlt: "Industria cărbunelui și oțelului"
      },
      {
        content: "Sprijinul SUA și Planul Marshall: În 1947, SUA au oferit un ajutor financiar de 12 miliarde de dolari pentru refacerea Europei. Statele aflate sub dominația sovietică au refuzat acest ajutor, iar pentru gestionarea fondurilor s-a înființat Organizația Europeană de Cooperare Economică (OECE), care s-a transformat în OCDE în 1961. De asemenea, Consiliul Europei, înființat în 1949, și-a propus apărarea democrației și a drepturilor omului, instituind Curtea Europeană a Drepturilor Omului (CEDO).",
        imageUrl: "https://c8.alamy.com/comp/BJN781/postwar-period-emblem-of-the-marshall-plan-erp-european-recovery-program-BJN781.jpg",
        imageAlt: "Planul Marshall și logo-ul OCDE"
      }
    ];
  
    // Actualizăm și chestionarul pentru a reflecta noua lecție
    const quizQuestions = [
      {
        question: "Care dintre următoarele a contribuit la unitatea europeană încă din antichitate?",
        options: [
          "Imperiul Roman",
          "Creștinismul",
          "Imperiile medievale",
          "Planul Marshall"
        ],
        correctAnswer: 0,
        explanation: "Imperiul Roman a răspândit limba latină și dreptul roman, contribuind la unitatea culturală și juridică a Europei."
      },
      {
        question: "Ce a creat o unitate culturală a Europei?",
        options: [
          "Imperiul Roman",
          "Creștinismul",
          "Planul Marshall",
          "OCDE"
        ],
        correctAnswer: 1,
        explanation: "Creștinismul a avut un rol esențial în unificarea culturală a Europei."
      },
      {
        question: "Cine a folosit expresia 'Statele unite ale Europei'?",
        options: [
          "Napoleon Bonaparte",
          "Victor Hugo",
          "Charles de Gaulle",
          "Winston Churchill"
        ],
        correctAnswer: 1,
        explanation: "Victor Hugo a folosit această expresie în 1849 pentru a exprima ideea unei Europe unite."
      },
      {
        question: "Care a fost una dintre cauzele creării Uniunii Europene menționată în lecție?",
        options: [
          "Renașterea",
          "Cele două războaie mondiale",
          "Revoluția Industrială",
          "Războiul Rece"
        ],
        correctAnswer: 1,
        explanation: "Cele două războaie mondiale au evidențiat necesitatea unui cadru de cooperare europeană."
      },
      {
        question: "Care a fost unul dintre obiectivele creării Uniunii Europene menționate în lecție?",
        options: [
          "Rezolvarea conflictului Franco-German",
          "Unificarea industriei auto",
          "Promovarea artei",
          "Extinderea granițelor"
        ],
        correctAnswer: 0,
        explanation: "Unificarea industriei cărbunelui și oțelului a fost esențială pentru rezolvarea conflictului Franco-German."
      },
      {
        question: "Ce a fost Planul Marshall (1947)?",
        options: [
          "O inițiativă economică de ajutorare a Europei",
          "Un tratat de pace",
          "O alianță militară",
          "O reformă educațională"
        ],
        correctAnswer: 0,
        explanation: "Planul Marshall a oferit 12 miliarde de dolari pentru refacerea economică a Europei după cel de-al Doilea Război Mondial."
      },
      {
        question: "Ce instituție din Consiliul Europei poate fi accesată de cetățeni pentru a-și proteja drepturile?",
        options: [
          "Parlamentul European",
          "Curtea Europeană a Drepturilor Omului (CEDO)",
          "Consiliul Național",
          "Comisia Europeană"
        ],
        correctAnswer: 1,
        explanation: "CEDO permite oricărui cetățean al unei țări membre să conteste încălcarea drepturilor sale."
      }
    ];
  
    let currentGroupIndex = 0;
    const itemsPerPage = 3;
    let direction = 'forward';
    let animateNext = false;
    let animatePrev = false;
    let showQuiz = false;
    let currentQuestionIndex = 0;
    let selectedAnswer = null;
    let score = 0;
  
    function nextGroup() {
      direction = 'forward';
      if ((currentGroupIndex + 1) * itemsPerPage < sections.length) {
        currentGroupIndex++;
      }
    }
  
    function previousGroup() {
      direction = 'backward';
      if (currentGroupIndex > 0) {
        currentGroupIndex--;
      }
    }
  
    function handleNext() {
      animateNext = true;
      nextGroup();
    }
  
    function handlePrev() {
      animatePrev = true;
      previousGroup();
    }
  
    function startQuiz() {
      showQuiz = true;
    }
  
    function handleAnswer(index) {
      if (selectedAnswer !== null) return;
      selectedAnswer = index;
      if (index === quizQuestions[currentQuestionIndex].correctAnswer) score++;
    }
  
    function nextQuestion() {
      if (currentQuestionIndex < quizQuestions.length - 1) {
        currentQuestionIndex++;
        selectedAnswer = null;
      } else {
        currentQuestionIndex++;
      }
    }
  
    $: canGoBack = currentGroupIndex > 0;
    $: canGoNext = (currentGroupIndex + 1) * itemsPerPage < sections.length;
  </script>
  
  <div class="p-5 -mt-20 fade-in">
    {#if !showQuiz}
      <p class="text-4xl font-bold text-white text-outline mb-8 text-center">
        {title}
      </p>
  
      {#key currentGroupIndex}
        <div>
          {#each sections.slice(currentGroupIndex * itemsPerPage, (currentGroupIndex + 1) * itemsPerPage) as section}
            <div class="flex flex-wrap justify-center items-center gap-8 lg:gap-12 mb-10">
              <div class="min-w-[300px] max-w-4xl flex-1">
                <p class="text-2xl text-white text-outline font-bold text-center lg:text-left">
                  {section.content}
                </p>
              </div>
              <img 
                src={section.imageUrl} 
                alt={section.imageAlt} 
                class="h-60 lg:h-80 w-auto rounded-2xl border-4 border-[#125768] shrink-0 transition-all"
                loading="lazy"
              >
            </div>
          {/each}
        </div>
      {/key}
  
      {#if canGoBack}
        <button
          on:click={handlePrev}
          on:animationend={() => animatePrev = false}
          class="fixed left-8 top-1/2 -translate-y-1/2 bg-white/30 rounded-full p-2 hover:bg-white/50 transition-colors arrow-button"
          class:animate-arrow={animatePrev}
          aria-label="Secțiuni precedente"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M19 12H5M12 19l-7-7 7-7"/>
          </svg>
        </button>
      {/if}
  
      {#if canGoNext}
        <button
          on:click={handleNext}
          on:animationend={() => animateNext = false}
          class="fixed right-8 top-1/2 -translate-y-1/2 bg-white/30 rounded-full p-2 hover:bg-white/50 transition-colors arrow-button"
          class:animate-arrow={animateNext}
          aria-label="Secțiuni următoare"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M5 12h14M12 5l7 7-7 7"/>
          </svg>
        </button>
      {/if}
  
      {#if (currentGroupIndex + 1) * itemsPerPage >= sections.length && !showQuiz}
        <!-- Butonul de chestionar plasat fix, în dreapta mijloc -->
        <button
          on:click={startQuiz}
          class="fixed right-8 top-1/2 -translate-y-1/2 bg-white/30 rounded-full p-2 hover:bg-white/50 transition-colors quiz-arrow-button animate-arrow"
          aria-label="Începe chestionarul"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M5 12h14M12 5l7 7-7 7"/>
          </svg>
        </button>
      {/if}
    {:else}
      <div class="quiz-container max-w-4xl mx-auto p-6">
        {#if currentQuestionIndex < quizQuestions.length}
          <div class="bg-white/30 backdrop-blur-lg rounded-2xl p-8 shadow-xl mb-8">
            <div class="text-white text-outline mb-6">
              <h3 class="text-2xl font-bold mb-2">Întrebarea {currentQuestionIndex + 1}/{quizQuestions.length}</h3>
              <p class="text-xl leading-relaxed">{quizQuestions[currentQuestionIndex].question}</p>
            </div>
  
            <div class="grid gap-4 mb-8">
              {#each quizQuestions[currentQuestionIndex].options as option, index (index)}
                <button
                  class="option-btn text-outline relative p-4 text-left rounded-xl transition-all"
                  class:correct={selectedAnswer !== null && index === quizQuestions[currentQuestionIndex].correctAnswer}
                  class:incorrect={selectedAnswer === index && index !== quizQuestions[currentQuestionIndex].correctAnswer}
                  on:click={() => handleAnswer(index)}
                  disabled={selectedAnswer !== null}
                >
                  <span class="mr-4 font-bold">{String.fromCharCode(65 + index)}.</span>
                  {option}
                </button>
              {/each}
            </div>
  
            {#if selectedAnswer !== null}
              <div class="pt-6 border-t-2 border-[#125768]/50">
                <div class:correct={selectedAnswer === quizQuestions[currentQuestionIndex].correctAnswer} class:incorrect={selectedAnswer !== quizQuestions[currentQuestionIndex].correctAnswer} class="feedback-message p-4 rounded-lg mb-6">
                  {#if selectedAnswer === quizQuestions[currentQuestionIndex].correctAnswer}
                    ✓ Corect! 
                  {:else}
                    ✗ Incorect. 
                  {/if}
                  {quizQuestions[currentQuestionIndex].explanation}
                </div>
  
                <button 
                  on:click={nextQuestion}
                  class="next-question-btn w-full py-3 rounded-lg bg-[#125768] hover:bg-[#1a7f94] transition-colors text-white font-bold"
                >
                  {currentQuestionIndex < quizQuestions.length - 1 ? 'Următoarea întrebare ➔' : 'Vezi rezultatul'}
                </button>
              </div>
            {/if}
          </div>
        {:else}
          <div class="text-center bg-white/30 backdrop-blur-md rounded-2xl p-12 shadow-xl animate-fade-in">
            <h2 class="text-3xl text-white text-outline font-bold mb-6">Felicitări! 🎉</h2>
            <div class="text-5xl text-white text-outline font-bold mb-8">{score}/{quizQuestions.length}</div>
            <p class="text-xl text-white text-outline mb-8">
              {#if score === quizQuestions.length}
                Performanță remarcabilă! Ai o cunoaștere excelentă a istoriei europene!
              {:else if score >= quizQuestions.length * 0.6}
                Rezultat foarte bun! Continuă să explorezi tema!
              {:else}
                Bun început! Recomandăm recitirea materialului pentru consolidare.
              {/if}
            </p>
          </div>
        {/if}
      </div>
    {/if}
  </div>
  
  <style>
    .fade-in {
      animation: fadeIn 0.5s ease-in;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
  
    .text-outline {
      text-shadow: 
        -1px -1px 0 #000,  
        1px -1px 0 #000,
        -1px 1px 0 #000,
        1px 1px 0 #000;
    }
  
    .arrow-button, .quiz-arrow-button {
      filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.3));
      backdrop-filter: blur(2px);
      transition: transform 0.2s ease-in-out, background-color 0.2s ease;
    }
  
    .arrow-button:hover, .quiz-arrow-button:hover {
      transform: translateY(-50%) scale(1.1);
      background-color: rgba(255, 255, 255, 0.5);
    }
  
    .animate-arrow {
      animation: arrowClickAnim 300ms ease-out;
    }
  
    @keyframes arrowClickAnim {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
  
    .option-btn {
      background: rgba(255, 255, 255, 0.1);
      border: 2px solid #125768;
      color: white;
      font-size: 1.1rem;
    }
  
    .option-btn:hover:not(:disabled) {
      background: rgba(255, 255, 255, 0.2);
      transform: translateY(-2px);
    }
  
    .option-btn.correct {
      background: rgba(40, 167, 69, 0.3);
      border-color: #28a745;
    }
  
    .option-btn.incorrect {
      background: rgba(220, 53, 69, 0.3);
      border-color: #dc3545;
    }
  
    .feedback-message {
      background: rgba(255, 255, 255, 0.15);
      border-left: 4px solid;
    }
  
    .feedback-message.correct {
      border-color: #005a15;
      color: #009e32;
    }
  
    .feedback-message.incorrect {
      border-color: #dc3545;
      color: #850009;
    }
  
    .animate-fade-in {
      animation: fadeIn 0.6s ease-out;
    }
  
    @media (max-width: 768px) {
      .arrow-button, .quiz-arrow-button {
        width: 36px;
        height: 36px;
        padding: 6px;
      }
      
      .arrow-button svg, .quiz-arrow-button svg {
        width: 32px;
        height: 32px;
      }
      
      .text-4xl {
        font-size: 2rem;
      }
      
      .text-2xl {
        font-size: 1.25rem;
      }
      
      .quiz-container {
        padding: 1rem;
        width: 90%;
      }
    }
  </style>
  
  <slot />
  