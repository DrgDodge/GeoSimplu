<script>
  import "/src/app.css";

  export let title = "Hazarduri Naturale";

  export let sections = [
    {
      content: "Definiție: Hazardurile naturale sunt fenomene întâmplătoare cu efecte negative asupra mediului și societății. Acestea includ cutremure, erupții vulcanice, inundații și alte evenimente geologice și meteorologice extreme.",
      imageUrl: "https://quizizz.com/media/resource/gs/quizizz-media/quizzes/71861667-27b0-42d9-80eb-17d72859163d",
      imageAlt: "Ilustrație hazarduri naturale"
    },
    {
      content: "Tectonica plăcilor: Cutremurele și vulcanii sunt legate de mișcările plăcilor tectonice. Zona Benioff (55-60° înclinare) este locul unde plăcile se subduc, generând activitate seismică intensă.",
      imageUrl: "https://thumbs.dreamstime.com/b/principal-tectonic-plates-map-289941533.jpg",
      imageAlt: "Harta plăcilor tectonice"
    },
    {
      content: "Vulcanismul: Erupțiile vulcanice (ex: Krakatoa 1883, St. Helens 1980) eliberează lavă, gaze și cenușă. Efecte includ opacitatea atmosferei și distrugerea ecosistemelor. Vulcanii activi sunt cei cu erupții în ultimele 2-3 generații.",
      imageUrl: "https://www.descopera.ro/wp-content/uploads/2016/02/15085849/2-vulcan-1.jpg",
      imageAlt: "Erupție vulcanică"
    },
    {
      content: "Cutremure: Măsurate cu scările Richter (magnitudine) și Mercalli (intensitate). Hipocentrul este focarul subteran, iar epicentrul punctul de la suprafață deasupra acestuia. Zona Vrancea este cea mai activă din România.",
      imageUrl: "https://www.infp.ro/img/teorie/image12.png",
      imageAlt: "Diagramă cutremur"
    },
    {
      content: "Alunecări de teren: Cauzate de instabilitatea versanților. Tipuri: curgeri de noroi (în zone argiloase), prăbușiri (zone cu roci dure). Pot bara râuri și distruge infrastructura.",
      imageUrl: "https://forestdesign.ro/images/blog/alunecari5.jpg",
      imageAlt: "Alunecare de teren"
    },
    {
      content: "Fenomene climatice: Ciclonii tropicali (ex: uragane) se formează în zonele intertropicale. Tornadele sunt frecvente în zonele temperate. Impact major asupra zonelor de coastă și agricultură.",
      imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Low_pressure_system_over_Iceland.jpg/1200px-Low_pressure_system_over_Iceland.jpg",
      imageAlt: "Ciclon tropical"
    },
    {
      content: "Riscuri hidrologice: Inundațiile pe Gange-Brahmaputra, Mississippi și Câmpia Chinei. Cauze: precipitații excesive și topirea zăpezilor.",
      imageUrl: "https://tb.ziareromania.ro/Inundatii-majore-in-Georgia---patru-morti/140471134f5b02e246/400/225/2/100/Inundatii-majore-in-Georgia---patru-morti.jpg",
      imageAlt: "Inundații majore"
    },
    {
      content: "Dezertificare: Proces natural amplificat de agricultura nesustenabilă. Peste 40% din suprafața terestră este afectată. Solul pierde fertilitatea datorită aridizării.",
      imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/94/ShrinkingLakeChad-1973-1997-EO.jpg/250px-ShrinkingLakeChad-1973-1997-EO.jpg",
      imageAlt: "Proces de dezertificare"
    },
    {
      content: "Prevenire: Sisteme de avertizare timpurie, construcții antiseismice, management al pădurilor. Educația populației reduce riscurile.",
      imageUrl: "https://0.academia-photos.com/attachment_thumbnails/39009458/mini_magick20190223-27869-nic1yu.png?1550961482",
      imageAlt: "Măsuri de prevenire"
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
      question: "Care este principala cauză a cutremurelor?",
      options: [
        "Erupții vulcanice",
        "Mișcări ale plăcilor tectonice",
        "Schimbări climatice",
        "Activități umane"
      ],
      correctAnswer: 1,
      explanation: "Cutremurele sunt cauzate de mișcările bruște ale plăcilor tectonice, în special în zonele de subducție."
    },
    {
      question: "Ce măsoară scara Richter?",
      options: [
        "Intensitatea seismică",
        "Magnitudinea energiei eliberate",
        "Adâncimea hipocentrului",
        "Durata cutremurului"
      ],
      correctAnswer: 1,
      explanation: "Scara Richter măsoară energia eliberată de cutremur (magnitudine), în timp ce scara Mercalli evaluează intensitatea percepută."
    },
    {
      question: "Care fenomen NU este considerat hazard natural?",
      options: [
        "Tsunami",
        "Erupție vulcanică",
        "Poluare industrială",
        "Ciclon tropical"
      ],
      correctAnswer: 2,
      explanation: "Poluarea industrială este un hazard antropic, nu natural."
    },
    {
      question: "Unde se formează ciclonii tropicali?",
      options: [
        "La poli",
        "În zonele temperate",
        "În zona intertropicală",
        "În deșerturi"
      ],
      correctAnswer: 2,
      explanation: "Ciclonii tropicali se formează în zona intertropicală datorită temperaturilor ridicate ale oceanului."
    },
    {
      question: "Ce procent din suprafața terestră este afectat de dezertificare?",
      options: ["10%", "25%", "40%", "60%"],
      correctAnswer: 2,
      explanation: "Peste 40% din suprafața terestră suferă de procese de aridizare și degradare a solului."
    },
    {
      question: "Care este zona seismică cea mai activă din România?",
      options: [
        "Munții Apuseni",
        "Depresiunea Transilvaniei",
        "Zona Vrancea",
        "Delta Dunării"
      ],
      correctAnswer: 2,
      explanation: "Zona Vrancea este cunoscută pentru activitatea seismică intensă datorită subducției plăcii continentale."
    },
    {
      question: "Ce efect au erupțiile vulcanice asupra atmosferei?",
      options: [
        "Crește nivelul oxigenului",
        "Diminuează radiațiile solare",
        "Reduce poluarea",
        "Crește temperatura globală"
      ],
      correctAnswer: 1,
      explanation: "Cenușa și gazele vulcanice reduc transparența atmosferei, blocând radiațiile solare."
    },
    {
      question: "Ce tip de alunecare de teren este specific zonelor argiloase?",
      options: [
        "Prăbușiri",
        "Curgere de noroi",
        "Avalanșe",
        "Eroziune"
      ],
      correctAnswer: 1,
      explanation: "Zonele cu substrat argilos sunt predispuse la curgeri de noroi datorită comportamentului plastic al solului."
    }
  ];

  // Funcțiile rămân neschimbate
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

<!-- Structura HTML rămâne identică cu ajustări minore pentru conținut -->
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

    <!-- Butoanele de navigație rămân aceleași -->
    {#if canGoBack}
      <button
        on:click={handlePrev}
        class="fixed left-8 top-1/2 -translate-y-1/2 bg-white/30 rounded-full p-2 hover:bg-white/50 transition-colors arrow-button"
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
        class="fixed right-8 top-1/2 -translate-y-1/2 bg-white/30 rounded-full p-2 hover:bg-white/50 transition-colors arrow-button"
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
            <h3 class="text-2xl font-bold mb-2">Întrebarea {currentQuestionIndex + 1}/8</h3>
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
          <div class="text-5xl text-white text-outline font-bold mb-8">{score}/8</div>
          <p class="text-xl text-white text-outline mb-8">
            {#if score === 8}
              Performanță remarcabilă! Ai o înțelegere profundă a hazardurilor naturale!
            {:else if score >= 5}
              Rezultat foarte bun! Cunoști esențialul despre riscurile naturale!
            {:else}
              Bun început! Recomandăm recitirea materialului pentru consolidare.
            {/if}
          </p>
        </div>
      {/if}
    </div>
  {/if}
</div>

<!-- Stilurile CSS rămân identice cu cele din exemplul anterior -->
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