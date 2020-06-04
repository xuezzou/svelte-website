<script>
const card_data = [
  {
    'title': 'Project 1',
    'icon': 'fas fa-font',
    'details': "Lorem ipsum dolor sit amet, elit.  \
                Pellentesque commodo quis enim quis rhoncus. Nunc consectetur \
                adipiscing vel ullamcorper arcu.",
    'color': '#e75d5d'
  },
  {
    'title': 'Project 2',
    'icon': 'fas fa-magic',
    'details': 'Lorem ipsum dolor sit amet, elit.  \
                Pellentesque commodo quis enim quis rhoncus. Nunc consectetur \
                adipiscing vel',
    'color': '#6fc0d1'
  },
  {
    'title': 'Project longer custom text',
    'icon': 'far fa-user',
    'details': 'Lorem ipsum dolor sit amet, elit.  \
                Pellentesque commodo quis enim quis rhoncus. Nunc consectetur \
                adipiscing vel ullamcorper arcu. Lorem',
    'color': '#7dc691'
  },
] 
</script>

<style>
* { box-sizing: border-box; }

.card-grid-view {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  
  margin: 1rem; 
}

.card-body {  
  border-radius: 4px;
  color: #bbbbc4;
  
  margin: 1.5rem;
  cursor: pointer;
  background: rgba(0, 0, 0, 0.2);

  /* margin-left: auto;
  margin-right: auto; */
  margin-top: 4rem;
  min-height: 30rem;

  transition: all 0.2s ease-out;
}
.card-body:hover {
  box-shadow: 0 0 2em 0px rgba(0, 0, 0, 0.3);
  transform: scale(1.01);
}
.card-body:active {
  transform: scale(1.01) translateY(0.2rem);
}
.card-body > .icon-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-body .icon { font-size: 3.5em; }

.card-body > .text-wrapper {
  padding: 1.5em;
  font-family: 'Lato';
  /* background-color: rgba(0, 0, 0, 0.2); */
  border-radius: 0 0 4px 4px;
}

.text-wrapper > .title {
  font-size: 1.3em;
  font-weight: bold;
  margin-bottom: 1.2em;
}
.text-wrapper > .details {
  font-size: 1.1em;
  line-height: 1.7em;
}
</style>

<!-- create a map -->
<!-- note that the cards are designed to be mult of 3 -->
<cards class="card-grid-view">
{#each card_data as item}
<div class="one-third column">
  <div class="card-body">
    <div class="icon-wrapper section">
      <span class="icon">
        <i class={item.icon} aria-hidden="true"></i>
      </span>
    </div>
    <div class="text-wrapper section">
      <div class="title"><span>{ item.title }</span></div>
      <div class="details"><span>{ item.details }</span></div>
    </div>
  </div>
</div>
{/each}
</cards>

