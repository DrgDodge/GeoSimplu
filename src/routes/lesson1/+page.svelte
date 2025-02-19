<script>
  import "/src/app.css";

  export let title = "Constituirea Uniunii Europene – O Călătorie Istorică";

  export let sections = [
    {
      content: "Introducere: Uniunea Europeană (UE) este o organizație supranațională formată din 27 de state membre, rezultatul unui proces complex de integrare care a transformat Europa. Totul a început la 9 mai 1950, când Declarația Schuman a propus unirea industriilor de cărbune și oțel pentru a asigura pacea pe continent.",
      imageUrl: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRkl74KUqCvQtDgLRXjvYuTSoz5B-Tbhc4BNg&s",
      imageAlt: "Harta Europei cu steagul UE"
    },
    {
      content: "Declarația Schuman (1950): La 9 mai 1950, ministrul francez al afacerilor externe, Robert Schuman, a prezentat un plan istoric de cooperare europeană, propunând plasarea producției de cărbune și oțel sub o autoritate comună, prevenind astfel conflictele viitoare.",
      imageUrl: "https://danutm.wordpress.com/wp-content/uploads/2015/01/schuman-declaration.jpg",
      imageAlt: "Portret istoric"
    },
    {
      content: "Tratatul de la Paris (1951) – Nașterea CECO: Pe 18 aprilie 1951, Franța, Germania de Vest, Italia, Belgia, Olanda și Luxemburg au semnat Tratatul de la Paris, înființând Comunitatea Europeană a Cărbunelui și Oțelului (CECO). Acest tratat a eliminat tarifele vamale și a pus bazele instituțiilor comune pentru gestionarea producției esențiale.",
      imageUrl: "https://www.cvce.eu/content/publication/1998/11/25/750bf92b-df2f-405c-ab1e-3b4f67129bc9/publishable.jpg",
      imageAlt: "Semnarea unui tratat"
    },
    {
      content: "Tratatul de la Roma (1957) – Formarea CEE: La 25 martie 1957, cele șase țări fondatoare au semnat Tratatele de la Roma, creând Comunitatea Economică Europeană (CEE) și Euratom. CEE a instaurat cele patru libertăți fundamentale: circulația persoanelor, mărfurilor, capitalurilor și serviciilor.",
      imageUrl: "https://dinculise.com/wp-content/uploads/2024/02/tratatul-de-la-roma-1957.jpeg",
      imageAlt: "Semnarea Tratatelor de la Roma"
    },
    {
      content: "Dezvoltarea și Extinderea Comunității Europene: De-a lungul decadelor, comunitatea a cunoscut multiple extinderi, incluzând aderările din 1973, 1981, 1986, 1995, 2004, 2007 și 2013. Aceste extinderi au consolidat piața unică și au promovat stabilitatea pe continent.",
      imageUrl: "https://upload.wikimedia.org/wikipedia/commons/e/ed/Enlargement_of_the_European_Union_77.gif",
      imageAlt: "Hartă a extinderii UE"
    },
    {
      content: "Tratatul de la Maastricht (1992) – Nașterea Uniunii Europene: Semnat în 1992 și intrat în vigoare în 1993, Tratatul de la Maastricht a transformat Comunitatea Economică Europeană în Uniunea Europeană. Acesta a extins cooperarea în domenii precum politica externă și de securitate și a stabilit criteriile pentru adoptarea monedei unice.",
      imageUrl: "https://www.caleaeuropeana.ro/wp-content/uploads/2018/02/semnarea-tratatului-de-la-maastricht.jpg",
      imageAlt: "Tratatele de la Maastricht"
    },
    {
      content: "Introducerea Monedei Euro (1999-2002): În 1999, moneda unică euro a fost introdusă pentru tranzacții electronice, iar în 2002 au fost puse în circulație bancnotele și monedele euro, facilitând comerțul și integrarea economică.",
      imageUrl: "https://media.evz.ro/wp-content/uploads/2023/06/euro-digital.jpg",
      imageAlt: "Monede și bancnote euro"
    },
    {
      content: "Acordurile Schengen (1995) și Libertatea de Mișcare: Implementate în 1995, Acordurile Schengen au eliminat controalele la frontierele interne, permițând cetățenilor UE să se deplaseze liber în spațiul Schengen.",
      imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/Schengen_Agreement_%281985%29_signatures.jpg/250px-Schengen_Agreement_%281985%29_signatures.jpg",
      imageAlt: "Frontieră deschisă"
    },
    {
      content: "Concluzie: Constituirea Uniunii Europene este o poveste de integrare, cooperare și solidaritate, care a dus la crearea unui spațiu de pace și prosperitate pe continent.",
      imageUrl: "https://cdn.economedia.ro/wp-content/uploads/2024/06/dreamstime_xl_61190226.webp",
      imageAlt: "Diversitate și unitate europeană"
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

  const quizQuestions = [
    {
      question: "Care eveniment este considerat punctul de start al Uniunii Europene?",
      options: [
        "Tratatul de la Roma",
        "Declarația Schuman", 
        "Tratatul de la Maastricht",
        "Acordurile Schengen"
      ],
      correctAnswer: 1,
      explanation: "Declarația Schuman din 9 mai 1950 a propus crearea Comunității Europene a Cărbunelui și Oțelului, marcând începutul procesului de integrare europeană."
    },
    {
      question: "Câte state fondatoare au semnat Tratatul de la Paris în 1951?",
      options: ["4", "6", "8", "10"],
      correctAnswer: 1,
      explanation: "Țările fondatoare au fost Franța, Germania de Vest, Italia, Belgia, Olanda și Luxemburg - total 6 state."
    },
    {
      question: "Care dintre acestea a fost principalul obiectiv al CECO?",
      options: [
        "Crearea unei monede unice",
        "Controlul comun al producției de cărbune și oțel",
        "Eliminarea frontierelor",
        "Cooperarea militară"
      ],
      correctAnswer: 1,
      explanation: "CECO a avut ca scop gestionarea comună a resurselor strategice de cărbune și oțel pentru a preveni conflictele."
    },
    {
      question: "Ce au instituit Tratatele de la Roma din 1957?",
      options: [
        "Uniunea Monetară Europeană",
        "CEE și Euratom",
        "Politica Agricolă Comună",
        "Spațiul Schengen"
      ],
      correctAnswer: 1,
      explanation: "Tratatele de la Roma au înființat Comunitatea Economică Europeană (CEE) și Comunitatea Europeană a Energiei Atomice (Euratom)."
    },
    {
      question: "Care tratat a creat oficial Uniunea Europeană?",
      options: [
        "Tratatul de la Paris",
        "Tratatul de la Roma",
        "Tratatul de la Maastricht",
        "Tratatul de la Lisabona"
      ],
      correctAnswer: 2,
      explanation: "Tratatul de la Maastricht din 1992 a transformat Comunitatea Europeană în Uniunea Europeană."
    },
    {
      question: "Când a fost introdus euro ca monedă fizică?",
      options: ["1999", "2001", "2002", "2005"],
      correctAnswer: 2,
      explanation: "Euro a fost introdus pentru tranzacții electronice în 1999, iar bancnotele și monedele au apărut în 2002."
    },
    {
      question: "Ce permite Acordul Schengen?",
      options: [
        "Monedă unică",
        "Circulație liberă fără controale la frontiere",
        "Politică externă comună",
        "Taxe vamale comune"
      ],
      correctAnswer: 1,
      explanation: "Acordurile Schengen au eliminat controalele sistematice la frontierele interne."
    },
    {
      question: "Care a fost primul val major de extindere a UE?",
      options: ["1973", "1981", "2004", "2007"],
      correctAnswer: 2,
      explanation: "Extinderea din 2004 a adus 10 noi state membre, majoritatea din Europa Centrală și de Est."
    },
    {
      question: "Câte state membre are UE în 2024?",
      options: ["25", "27", "29", "31"],
      correctAnswer: 1,
      explanation: "După Brexit (ieșirea Regatului Unit), UE are 27 de state membre."
    }
  ];

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
            <h3 class="text-2xl font-bold mb-2">Întrebarea {currentQuestionIndex + 1}/9</h3>
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
          <div class="text-5xl text-white text-outline font-bold mb-8">{score}/9</div>
          <p class="text-xl text-white text-outline mb-8">
            {#if score === 9}
              Performanță remarcabilă! Ai o cunoaștere excelentă a istoriei UE!
            {:else if score >= 6}
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
