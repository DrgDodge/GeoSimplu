<script>
        import "/src/app.css";
    // Main title for the page
    export let title = "Constituirea Uniunii Europene – O Călătorie Istorică";
  
    // Array with three sections, each with its own text and image data
    export let sections = [
      {
        content:
          "UE este o organizație supra-statală formată din 27 de state. Punctul de plecare în constituirea Uniunii Europene l-a reprezentat Declarația Schuman de la data de 9 mai 1950, prin care statele Europei de Vest erau invitate să-și unească industriile cărbunelui și oțelului.",
        imageUrl: "/images/eu1.png",
        imageAlt: "Harta UE 1"
      },
      {
        content:
          "A doua secțiune a lecției discută integrarea economică și politică în UE, subliniind colaborarea dintre statele membre și beneficiile unei piețe comune.",
        imageUrl: "/images/eu1.png",
        imageAlt: "Harta UE 2"
      },
      {
        content:
          "A treia secțiune evidențiază provocările și perspectivele viitoare ale Uniunii Europene, accentuând schimbările socio-economice și impactul global.",
        imageUrl: "/images/eu3.png",
        imageAlt: "Harta UE 3"
      }
    ];
  </script>
  
  <div class="p-5 -mt-20 fade-in">
    <!-- Title placed at the very top, centered with no extra space above -->
    <p class="text-4xl font-bold text-white text-outline mb-8 text-center">
      {title}
    </p>
  
    <!-- Iterate over each section to display text and image -->
    {#each sections as section}
      <div class="flex flex-wrap justify-center items-center gap-8 lg:gap-12 mb-10">
        <!-- Text container -->
        <div class="min-w-[300px] max-w-4xl flex-1">
          <p class="text-2xl text-white text-outline font-bold text-center lg:text-left">
            {section.content}
          </p>
        </div>
  
        <!-- Responsive image -->
        <img 
          src={section.imageUrl} 
          alt={section.imageAlt} 
          class="h-60 lg:h-80 w-auto rounded-2xl border-4 border-[#125768] shrink-0 transition-all"
        >
      </div>
    {/each}
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
  </style>
  
  <slot />
  