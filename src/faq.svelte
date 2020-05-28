<script>
  export let questionSet;
  export let identifier;

  import { tick } from 'svelte';

  let group = [];
  
  let uncheck = () =>{
    if(group.length >= 1 &&group[0] !== event.srcElement.value){
      group.push(event.srcElement.value);
      group.shift(); 
      group=group;
    }
  }
  
</script>

<style>
.faq-header{
}

.faq-content {
}

.faq-question {
}

.panel-title {
  font-size: 1.8rem;
  font-weight: normal;
  color: #bbbbc4;
  position: relative;
  margin: 0;
  padding: 1.2rem 1rem 0 2.6rem;
  display: block;
  cursor: pointer;
  margin-right: 2rem;
}

.panel-content {
  color: #bbbbc4;
  font-size: 1.2rem;
  padding: 0 1rem;
  margin: 0 2rem;
  height: 0;
  overflow: hidden;
  z-index: -1;
  position: relative;
  opacity: 0;
  -webkit-transition: .4s ease;
  -moz-transition: .4s ease;
  -o-transition: .4s ease;
  transition: .4s ease;
}

.panel-title:hover {
  color: #ffdb73;
}
.panel:hover ~ .plus{
  color: #ffdb73;
}

.panel:checked ~ .panel-title{
  color: white;
}
.panel:checked ~ .plus{
  color: #ffdb73;
}
.panel:checked ~ .panel-content{
  height: auto;
  opacity: 1;
  padding: 14px;
}

.plus {
  color: white;
  position: absolute;
  margin-left: 0.5rem;
  margin-top: 1.5rem;
  z-index: 5;
  font-size: 2.2rem;
  line-height: 100%;
  -webkit-user-select: none;    
  -moz-user-select: none;
  -ms-user-select: none;
  -o-user-select: none;
  user-select: none;
  -webkit-transition: .2s ease;
  -moz-transition: .2s easße;
  -o-transition: .2s ease;
  transition: .2s ease;
}

.panel:checked ~ .plus {
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -o-transform: rotate(45deg);
  transform: rotate(45deg);
}

.panel {
  display: none;
}
</style>

<faqItems>
  <div class="faq-content">
    {#if questionSet}
      {#each questionSet as item, i}
        <div class="faq-question">
          <input id={identifier}{i} type="checkbox" class="panel" bind:group={group} value={item.question} 
            on:click={uncheck}>
          <div class="plus">+</div>
          <label for={identifier}{i} class="panel-title">{item.question}</label>
          <div class="panel-content">{item.answer}</div>
        </div>
      {/each}
    {/if}
  </div>
</faqItems>
