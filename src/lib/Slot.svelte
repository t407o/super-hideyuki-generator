<script lang="ts">
  let hide: string = "ひで";
  let yuki: string = "ゆき";
  let hideyuki: string = undefined;
  const genHideyuki = () => {
    hide = genKanji(HIDES);
    yuki = genKanji(YUKIS);
    hideyuki = hide + yuki;
  };

  const genKanji = (dataset: string[]) => {
    return dataset[random(dataset.length)];
  };

  const random = (i: number) => {
    return Math.floor(Math.random() * i);
  };

  const HIDES = [
    "英",
    "秀",
    "英",
    "日出",
    "偉",
    "映",
    "栄",
    "任",
    "継",
    "HIDE",
  ];
  const YUKIS = [
    "行",
    "幸",
    "征",
    "之",
    "享",
    "淑",
    "豪",
    "侑",
    "如",
    "志",
    "往",
    "維",
    "雪",
    "将",
    "秀",
    "介",
    "由紀",
    "礼",
    "敬",
    "鵬",
    "進",
    "享",
    "YUKI",
  ];
</script>

{#if hideyuki}
  <p>
    今日から君は <b>"{hideyuki}" (ひでゆき)</b> だ！！
  </p>
{/if}
<button on:click={genHideyuki}> 漢字を得る </button>

{#if hideyuki}
  <p>
    Search the meaning of&nbsp;<a
      href="https://www.google.com/search?q={hide}"
      target="_blank">{hide}</a
    >
  </p>
  <p>
    Search the meaning of&nbsp;<a
      href="https://www.google.com/search?q={yuki}"
      target="_blank">{yuki}</a
    >
  </p>
{/if}

<style>
  p b {
    font-size: 200%;
  }
</style>
