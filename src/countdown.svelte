<script>
// Set the date we're counting down to
let countDownDate = new Date("June 27, 2020 00:00:00").getTime();

// Get today's date and time
let now = new Date().getTime();
setInterval(() => {now = new Date().getTime();}, 1000)
$: distance = countDownDate - now;

// Time calculations for days, hours, minutes and seconds
$: days = Math.floor(distance / (1000 * 60 * 60 * 24));
$: hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
$: minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
$: seconds = Math.floor((distance % (1000 * 60)) / 1000);

if (distance < 0) {

}
</script>

<style>

.figure {
  color: #ffdb73;
  font-size: 4rem;
  text-align: center;
  margin-top: 9rem;
  margin-right: 1.5rem;
}


@media (max-width: 550px) {
    .figure {
     margin-top: 0rem;
     text-align: left;
    } 
  }
</style>

<countdown>
  <h2 class="figure">
    {days}:
    {hours}:
    {minutes}:
    {seconds}
  </h2>
</countdown>