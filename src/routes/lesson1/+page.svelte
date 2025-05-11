<script>
  import "/src/app.css";

  export let title = "Presiunea Umană și Hazardurile Antropice";

  export let sections = [
    {
      content: "Introducere: Hazardurile antropice sunt evenimente accidentale cauzate de activități umane sau procese tehnologice. Acestea au impact major asupra mediului și societății, fiind rezultatul exploatării intensive a resurselor și industrializării.",
      imageUrl: "https://stratos.ro/wp-content/uploads/2021/09/Impactul-industriei-asupra-mediului-cum-poate-fi-controlat.jpg",
      imageAlt: "Poluare industrială"
    },
    {
      content: "Exploatarea resurselor: Procesul de exploatare include cercetarea, extragerea, crearea infrastructurii și generarea de deșeuri. Acest ciclu duce la modificări profunde ale peisajului natural și dezechilibre ecologice.",
      imageUrl: "https://storage0.dms.mpinteractiv.ro/media/401/781/10368/9359415/21/mina10.jpg",
      imageAlt: "Exploatare minieră"
    },
    {
      content: "Poluarea industrială: Industria siderurgică, chimică și energetică emit noxe care afectează aerul, apa și solul. Termocentralele sunt surse majore de CO2, contribuind la încălzirea globală.",
      imageUrl: "https://thumbs.dreamstime.com/b/fum-dintr-un-afluent-industrial-aprins%C4%83-de-centrul-floridei-turb%C4%83rii-la-stivele-unei-centrale-electrice-pe-baz%C4%83-c%C4%83rbune-28862241.jpg",
      imageAlt: "Fum industrial"
    },
    {
      content: "Accidente petroliere: Deversările din petroliere (Exxon Valdez, 1989) sau platforme offshore cauzează dezastre ecologice pe termen lung. Un litru de petrol poate contamina 1 milion de litri de apă.",
      imageUrl: "https://s.iw.ro/gateway/g/ZmlsZVNvdXJjZT1odHRwJTNBJTJGJTJG/c3RvcmFnZTA4dHJhbnNjb2Rlci5yY3Mt/cmRzLnJvJTJGc3RvcmFnZSUyRjIwMjQl/MkYwMiUyRjEzJTJGMTkwMjcyNF8xOTAy/NzI0X2RldmVyc2FyZS1wZXRyb2wtdHJp/bmlkYWQtdG9iYWdvLmpwZyZ3PTc4MCZo/PTQ0MCZoYXNoPTA0YjE0MTgzMmNmYjBmOTgxNWRiYTE5OWE2NmRjNDQy.thumb.jpg",
      imageAlt: "Deversare petrolieră"
    },
    {
      content: "Hazarduri nucleare: Accidentul de la Cernobîl (1986) a eliberat radiații echivalente cu 400 de bombe atomice. Zona de excludere rămâne inabitabilă timp de mii de ani.",
      imageUrl: "https://www.descopera.ro/wp-content/uploads/2024/11/cernobil-zona-excludere-shutter_Descopera-scaled.jpg",
      imageAlt: "Zona Cernobîl"
    },
    {
      content: "Urbanizarea: Extinderea orașelor duce la artificializarea solului, poluare fonnică și generarea de deșeuri menajere. 60% din emisiile globale de CO2 provin din zone urbane.",
      imageUrl: "https://img.rockwool.com/https%3A%2F%2Fbrandcommunity.rockwool.com%2Fasset%2FGH31DmIaRwE07w17OjyWuw?ar=16%3A9&fit=crop&w=1120&rect=0.0000%2C0.077177%2C4000%2C2250&auto=format&s=afacc8cf3a0c8c0a4e23c0da2a32a939",
      imageAlt: "Urbanizare intensă"
    },
    {
      content: "Deșertificarea: Agricultura nesustenabilă și defrișările intensive accelerează degradarea solului. Peste 40% din suprafața terestră este afectată de aridizare.",
      imageUrl: "https://kaputt-sekuro.ro/wp-content/uploads/2025/01/desertificarea.jpeg",
      imageAlt: "Proces de deșertificare"
    },
    {
      content: "Transporturi periculoase: Accidentele rutiere sau feroviare cu substanțe toxice (ex: deraieri de trenuri chimice) creează zone de contaminare cu efecte asupra sănătății umane.",
      imageUrl: "https://hotnews.ro/wp-content/uploads/2024/04/image-2023-03-1-26115233-41-accident-feroviar-grecia-2.jpg",
      imageAlt: "Accident feroviar"
    },
    {
      content: "Prevenire și management: Implementarea tehnologiilor verzi, sisteme de alarmă timpurie și educarea populației reduc riscurile. Reciclarea 80% din deșeuri industriale poate diminua impactul.",
      imageUrl: "https://marathonepr.ro/wp-content/uploads/2022/11/simbolurilereciclarii_01.webp",
      imageAlt: "Simbol reciclare"
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
      question: "Care este principalul factor al hazardurilor antropice?",
      options: [
        "Fenomene naturale",
        "Activități umane",
        "Schimbări climatice",
        "Erupții vulcanice"
      ],
      correctAnswer: 1,
      explanation: "Hazardurile antropice sunt cauzate direct de activități umane și procese tehnologice."
    },
    {
      question: "Care a fost cel mai grav accident nuclear?",
      options: [
        "Fukushima (2011)",
        "Three Mile Island (1979)",
        "Cernobîl (1986)",
        "Windscale (1957)"
      ],
      correctAnswer: 2,
      explanation: "Accidentul de la Cernobîl a eliberat cea mai mare cantitate de material radioactiv din istorie."
    },
    {
      question: "Ce provoacă deșertificarea?",
      options: [
        "Precipitații excesive",
        "Agricultura intensivă",
        "Reforestare",
        "Energia eoliană"
      ],
      correctAnswer: 1,
      explanation: "Practicile agricole nesustenabile și defrișările sunt cauze primare ale deșertificării."
    },
    {
      question: "Câți litri de apă contaminează 1 litru de petrol?",
      options: ["1.000", "10.000", "100.000", "1.000.000"],
      correctAnswer: 3,
      explanation: "Un singur litru de petrol poate face 1 milion de litri de apă nepotabilă."
    },
    {
      question: "Ce procent din CO2 provine din zone urbane?",
      options: ["30%", "60%", "45%", "75%"],
      correctAnswer: 1,
      explanation: "Urbanizarea intensă și consumul de energie în orașe contribuie cu 60% la emisiile globale."
    },
    {
      question: "Care NU este hazard antropic?",
      options: [
        "Deversare petrolieră",
        "Poluare radioactivă",
        "Alunecare de teren",
        "Explozie industrială"
      ],
      correctAnswer: 2,
      explanation: "Alunecările de teren sunt hazard natural, nelegat de activitatea umană."
    },
    {
      question: "Când a avut loc accidentul Exxon Valdez?",
      options: ["1979", "1989", "1999", "2009"],
      correctAnswer: 1,
      explanation: "Nava Exxon Valdez a deversat peste 40 de milioane de litri de petrol în 1989 în Alaska."
    },
    {
      question: "Ce măsură previne hazardurile antropice?",
      options: [
        "Extinderea industrială",
        "Sisteme de alarmă timpurie",
        "Creșterea consumului",
        "Exploatare intensivă"
      ],
      correctAnswer: 1,
      explanation: "Sistemele de monitorizare și alarmă reduc impactul accidentelor tehnologice."
    },
    {
      question: "Ce procent din sol este afectat de deșertificare?",
      options: ["10%", "25%", "40%", "60%"],
      correctAnswer: 2,
      explanation: "Peste 40% din suprafața terestră este afectată de procese de aridizare și degradare a solului."
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
              Performanță remarcabilă! Ai o înțelegere profundă a hazardurilor antropice!
            {:else if score >= 6}
              Rezultat foarte bun! Cunoști esențialul despre impactul uman!
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