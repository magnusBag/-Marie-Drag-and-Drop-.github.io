<script>
  import DragItem from "./lib/dragItem.svelte";

  let questions = [
    {
      name: "Spørgsmål: Hvad er de tre elementer i Toulmins grundlæggende argumentationsmodel?",
    },
    { name: "Spørgsmål: Hvad kan man bruge Toulmins argumentationsmodel til?" },
    {
      name: "Spørgsmål: Hvad kræves der for at noget kan kaldes for et argument?",
    },
    { name: "Spørgsmål: Hvad er et arguments 'påstand'?" },
    { name: "Spørgsmål: Hvad er et arguments 'belæg'?" },
    { name: "Spørgsmål: Hvad er et arguments 'hjemmel'?" },
    {
      name: "Spørgsmål: Hvad kan man spørge om for at finde et arguments påstand?",
    },
    {
      name: "Spørgsmål: Hvad kan man spørge om for at finde et arguments belæg?",
    },
    {
      name: "Spørgsmål: Hvad kan man spørge om for at finde et arguments hjemmel?",
    },
  ];
  questions.forEach((item) => {
    item.answer = false;
  });
  let answers = [
    { name: "Svar: Påstand, belæg og hjemmel" },
    {
      name: "Svar: At analysere argumenter på flere niveauer - at undersøge og være kritisk over for måden der argumenteres på. At se argumenters struktur.",
    },
    {
      name: "Svar: Mindst to elementer: En påstand og et belæg. En påstand alene er et postulat.",
    },
    {
      name: "Svar: Afsenders synspunkt. Det som afsenderen ønsker at vinde tilslutning til.",
    },
    {
      name: "Svar: Direkte støtte for påstanden. Der kan godt findes flere belæg pr. argument.",
    },
    {
      name: "Svar: Leddet, som forbinder påstand og belæg. Et generelt synspunkt, som afsender og modtager deler. Ofte underforstået dvs. ikke sagt direkte i teksten.",
    },
    { name: "Svar: 'Hvad ønsker afsender at vinde tilslutning til?'" },
    { name: "Svar: 'Hvad begrunder afsender påstanden med?'" },
    { name: "Svar: 'Hvordan skabes sammenhæng mellem belæg og påstand?'" },
  ];
  answers.forEach((item) => {
    item.answer = true;
  });
  questions = questions.sort(() => Math.random() - 0.5);
  answers = answers.sort(() => Math.random() - 0.5);
</script>

<div class="flex gap-4 m-2 justify-between">
  <div class="flex flex-wrap gap-2" id="answers">
    {#each questions as item}
      <DragItem {item} answer={item.answer} />
    {/each}
  </div>
  <div class="flex flex-wrap gap-2 justify-end">
    {#each answers as item}
      <DragItem {item} answer={item.answer} />
    {/each}
  </div>
</div>
