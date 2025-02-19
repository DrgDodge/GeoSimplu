<script>
    import "/src/app.css";
  
    export let title = "Instituțiile Uniunii Europene";
  
    export let sections = [
      {
        content: "Parlamentul European are sediul la Strasbourg și este format din membri aleși prin vot universal de cetățenii din țările UE. Numărul de parlamentari ai fiecărei țări este direct proporțional cu numărul locuitorilor. \n\nAtribuții: Votează legile UE și bugetul UE.",
        imageUrl: "https://www.forbes.ro/wp-content/uploads/2022/07/Parlamentul-European.jpg",
        imageAlt: "Parlamentul European, Strasbourg"
      },
      {
        content: "Comisia Europeană are sediul la Bruxelles și este alcătuită din câte un membru din fiecare țară, numit de guvernul țării respective. \n\nAtribuții: Propune proiecte de lege pentru Parlamentul European și urmărește punerea în aplicare a legilor și programelor UE.",
        imageUrl: "https://cdn.adh.reperio.news/image-b/bc5eb70d-85e8-461c-b802-fa206062eff7/index.jpeg?p=a%3D1%26co%3D1.05%26w%3D700%26h%3D750%26r%3Dcontain%26f%3Dwebp",
        imageAlt: "Comisia Europeană, Bruxelles"
      },
      {
        content: "Consiliul UE are sediul la Bruxelles și este format din miniștrii statelor membre, reuniți în funcție de problema discutată (agricultură, mediu, educație etc.). \n\nAtribuții: Adoptă regulamente și stabilește proiectul bugetului UE.",
        imageUrl: "https://www.caleaeuropeana.ro/wp-content/uploads/2016/12/15203165_1161374257245561_3383735731290230340_n.jpg",
        imageAlt: "Consiliul UE, Bruxelles"
      },
      {
        content: "Curtea de Justiție a UE, cu sediul la Luxemburg, este alcătuită din câte un judecător numit de fiecare stat membru pentru 6 ani. \n\nAtribuții: Asigură interpretarea și aplicarea corectă a legilor europene și garantează respectarea legislației UE de către statele membre.",
        imageUrl: "https://hotnews.ro/wp-content/uploads/2024/09/profimedia-0771254653.jpg?w=800&h=533&crop=1",
        imageAlt: "Curtea de Justiție a UE, Luxemburg"
      },
      {
        content: "Curtea de Conturi, situată la Luxemburg, este alcătuită din câte un membru din fiecare stat, numit de Consiliul de Miniștri pentru 6 ani. \n\nAtribuții: Urmărește utilizarea corectă a Fondurilor Europene de către statele membre.",
        imageUrl: "https://www.bursa.ro/_img/articole/mare/399308.jpg",
        imageAlt: "Curtea de Conturi, Luxemburg"
      },
      {
        content: "Consiliul European, cu sediul la Bruxelles, este alcătuit din șefii sau prim-miniștrii statelor membre și se întrunește cel puțin de 2 ori pe an. Fiecare stat deține președinția pentru 6 luni prin rotație. \n\nAtribuții: Stabilește politica generală a UE, inclusiv aderarea de noi state, adoptarea monedei euro de către noi state și extinderea spațiului Schengen.",
        imageUrl: "https://upload.wikimedia.org/wikipedia/commons/2/2e/Europa_building_February_2016_%28cropped%29.jpg",
        imageAlt: "Consiliul European, Bruxelles"
      },
      {
        content: "Banca Centrală Europeană are sediul la Frankfurt. \n\nAtribuții: Emite moneda euro, asigură stabilitatea prețurilor în zona euro, controlează inflația și protejează sistemul financiar și bancar al statelor membre.",
        imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/ECB_Frankfurt_at_Sunset.jpg/220px-ECB_Frankfurt_at_Sunset.jpg",
        imageAlt: "Banca Centrală Europeană, Frankfurt"
      },
      {
        content: "În prezent, moneda euro este folosită în 20 de state.",
        imageUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/65/Euro_coins_and_banknotes.jpg/640px-Euro_coins_and_banknotes.jpg",
        imageAlt: "Simbolul monedei euro"
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
  
    // Quiz questions based on the lecture content
    const quizQuestions = [
  {
    question: "Unde are sediul Parlamentul European și cum sunt aleși membrii săi?",
    options: [
      "Strasbourg, aleși prin vot universal",
      "Bruxelles, numiți de guverne",
      "Luxemburg, aleși de consilii locale",
      "Frankfurt, aleși prin vot direct"
    ],
    correctAnswer: 0,
    explanation: "Parlamentul European se află la Strasbourg, iar membrii săi sunt aleși prin vot universal, proporțional cu populația fiecărei țări."
  },
  {
    question: "Care este atribuția principală a Comisiei Europene?",
    options: [
      "Votează legile UE",
      "Propune proiecte de lege și monitorizează implementarea acestora",
      "Adoptă regulamente",
      "Interpretează legile UE"
    ],
    correctAnswer: 1,
    explanation: "Comisia Europeană propune proiecte de lege pentru Parlamentul European și se asigură că legile și programele UE sunt implementate corect."
  },
  {
    question: "Ce rol are Consiliul UE în procesul legislativ?",
    options: [
      "Elaborează bugetul UE",
      "Adoptă regulamente și stabilește proiectul bugetului UE",
      "Votează legile UE",
      "Interpretează legislația UE"
    ],
    correctAnswer: 1,
    explanation: "Consiliul UE, format din miniștrii statelor membre, adoptă regulamente și stabilește proiectul bugetului UE, în funcție de temele discutate."
  },
  {
    question: "Ce asigură Curtea de Justiție a UE?",
    options: [
      "Monitorizează finanțele UE",
      "Adoptă bugetul UE",
      "Interpretează și aplică corect legile europene",
      "Propune proiecte de lege"
    ],
    correctAnswer: 2,
    explanation: "Curtea de Justiție a UE interpretează și aplică corect legile europene, garantând respectarea acestora de către statele membre."
  },
  {
    question: "Ce urmărește Curtea de Conturi a UE?",
    options: [
      "Utilizarea corectă a Fondurilor Europene",
      "Controlul inflației",
      "Adoptarea regulilor bugetare",
      "Monitorizarea legislației UE"
    ],
    correctAnswer: 0,
    explanation: "Curtea de Conturi se asigură că Fondurile Europene sunt utilizate corect de către statele membre."
  },
  {
    question: "Ce stabilește Consiliul European?",
    options: [
      "Legislația națională a statelor membre",
      "Politica generală a UE, inclusiv criteriile de aderare și extinderea spațiului Schengen",
      "Regulamentele interne ale UE",
      "Procedurile de vot în Parlamentul European"
    ],
    correctAnswer: 1,
    explanation: "Consiliul European, alcătuit din șefii sau prim-miniștrii statelor membre, stabilește politica generală a UE, inclusiv aderarea de noi state și extinderea spațiului Schengen."
  },
  {
    question: "Care sunt principalele atribuții ale Băncii Centrale Europene?",
    options: [
      "Emite moneda euro și asigură stabilitatea prețurilor în zona euro",
      "Votează legile UE",
      "Propune proiecte de lege",
      "Interpretează legile europene"
    ],
    correctAnswer: 0,
    explanation: "Banca Centrală Europeană emite moneda euro și se asigură că prețurile din zona euro rămân stabile, controlând inflația și protejând sistemul financiar."
  },
  {
    question: "În câte state este utilizată moneda euro în prezent?",
    options: [
      "20",
      "25",
      "27",
      "30"
    ],
    correctAnswer: 0,
    explanation: "Moneda euro este folosită în prezent în 20 de state membre."
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
              <h3 class="text-2xl font-bold text-outline mb-2">Întrebarea {currentQuestionIndex + 1}/{quizQuestions.length}</h3>
              <p class="text-xl text-outline leading-relaxed">{quizQuestions[currentQuestionIndex].question}</p>
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
                Performanță remarcabilă! Ai o cunoaștere excelentă a instituțiilor UE!
              {:else if score >= Math.floor(quizQuestions.length * 0.6)}
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
  