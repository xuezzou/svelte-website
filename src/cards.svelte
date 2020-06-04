<script>
// note svg elements from here: https://github.com/Keyamoon/IcoMoon-Free/tree/master/SVG
const fillColor = '#555560';
const card_data = [
  {
    'title': 'Project 1',
    'icon': '<path fill="#555560" d="M13.5 0c1.381 0 2.5 1.119 2.5 2.5 0 0.563-0.186 1.082-0.5 1.5l-1 1-3.5-3.5 1-1c0.418-0.314 0.937-0.5 1.5-0.5zM1 11.5l-1 4.5 4.5-1 9.25-9.25-3.5-3.5-9.25 9.25zM11.181 5.681l-7 7-0.862-0.862 7-7 0.862 0.862z"/>',
    'details': "Lorem ipsum dolor sit amet, elit.  \
                Pellentesque commodo quis enim quis rhoncus. Nunc consectetur \
                adipiscing vel ullamcorper arcu. dipiscing vel ullamcorper arcu. ",
  },
  {
    'title': 'Project 2',
    'icon': '<path fill="#555560" d="M16 15v-1h-1v-6h1v-1h-3v1h1v6h-3v-6h1v-1h-3v1h1v6h-3v-6h1v-1h-3v1h1v6h-3v-6h1v-1h-3v1h1v6h-1v1h-1v1h17v-1h-1z"/> \
             <path fill="#555560" d="M8 0h1l8 5v1h-17v-1l8-5z"/>',
    'details': 'Lorem ipsum dolor sit amet, elit.  \
                Pellentesque commodo quis enim quis rhoncus. Nunc consectetur \
                adipiscing vel dipiscing vel ullamcorper arcu.',
  },
  {
    'title': 'Project longer custom text',
    'icon': '<path fill="#555560" d="M8 0c-4.418 0-8 3.582-8 8s3.582 8 8 8 8-3.582 8-8-3.582-8-8-8zM8 15c-0.984 0-1.92-0.203-2.769-0.57l3.643-4.098c0.081-0.092 0.126-0.21 0.126-0.332v-1.5c0-0.276-0.224-0.5-0.5-0.5-1.765 0-3.628-1.835-3.646-1.854-0.094-0.094-0.221-0.146-0.354-0.146h-2c-0.276 0-0.5 0.224-0.5 0.5v3c0 0.189 0.107 0.363 0.276 0.447l1.724 0.862v2.936c-1.813-1.265-3-3.366-3-5.745 0-1.074 0.242-2.091 0.674-3h1.826c0.133 0 0.26-0.053 0.354-0.146l2-2c0.094-0.094 0.146-0.221 0.146-0.354v-1.21c0.634-0.189 1.305-0.29 2-0.29 1.1 0 2.141 0.254 3.067 0.706-0.065 0.055-0.128 0.112-0.188 0.172-0.567 0.567-0.879 1.32-0.879 2.121s0.312 1.555 0.879 2.121c0.569 0.569 1.332 0.879 2.119 0.879 0.049 0 0.099-0.001 0.149-0.004 0.216 0.809 0.605 2.917-0.131 5.818-0.007 0.027-0.011 0.055-0.013 0.082-1.271 1.298-3.042 2.104-5.002 2.104z"/>',
    'details': 'Lorem ipsum dolor sit amet, elit.  \
                Pellentesque commodo quis enim quis rhoncus. Nunc consectetur \
                adipiscing vel ullamcorper arcu. Lorem dipiscing vel ullamcorper arcu.',
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

  /* margin-left: auto;
  margin-right: auto; */
  margin-top: 4rem;
  /* important variable */
  min-height: 35em;
  background-color: rgba(0, 0, 0, 0.2);

  transition: all 0.2s ease-out;
}
.card-body:hover {
  box-shadow: 0 0 2em 0px rgba(0, 0, 0, 0.4);
  transform: scale(1.01);
  background: #ffdb73;
  color: #32333a;
}

.card-body:active {
  transform: scale(1.01) translateY(0.2rem);
}
.card-body > .icon-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.2);
}
.card-body .icon { padding: 5.8rem 0; }

.card-body > .text-wrapper {
  padding: 1.5em;
  padding-bottom: 2.7rem;
  font-family: 'Lato';
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

@media (max-width: 550px) {
    .card-body {
      min-height: 0rem;
    } 
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
        <!-- <i class={item.icon} aria-hidden="true"></i> -->
        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="6rem" height="6rem" viewBox="0 0 16 16">
          {@html item.icon}
        </svg>
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

