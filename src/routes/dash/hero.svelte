<script>
    import { Card } from 'flowbite-svelte';

    let words = ["Innovative", "Weird", "Ambitious", "Young"];
    let currentIndex = 0;
  
    // Function to cycle through the words
    function cycleWords() {
      currentIndex = (currentIndex + 1) % words.length;
    }
  
    // Set an interval to change the word every 3 seconds
    let interval = setInterval(cycleWords, 3000);
  
    // Cleanup interval when component is destroyed
    import { onDestroy } from 'svelte';
    onDestroy(() => clearInterval(interval));
  </script>
  
  <style>
    .hero-card {
      position: relative;
      width: 100vw;
      overflow: hidden;
      display: flex;
      margin: 0 auto;
      width: 100%;
      justify-content: center;
      font-family: 'Brittany Signature', sans-serif;
    }
  
    .glitch {
      position: relative;
      color: #333;
      font-size: 40px;
      font-family: 'Bruno Ace', sans-serif;
      padding: 10px;
      text-shadow: 1px 0 rgb(0, 0, 0), -1px 0 rgb(0, 0, 0);
      animation: glitch 1s infinite;
    }
  
    .glitch:before, .glitch:after {
      content: attr(data-text);
      font-family: 'Bruno Ace', sans-serif;
      position: absolute;
      padding: 10px;
      top: 0;
      left: 0;
      color: #333;
      overflow: hidden;
      width: 100%;
      height: 100%;
    }
  
    .glitch:before {
      left: 2px;
      font-family: 'Bruno Ace', sans-serif;
      text-shadow: -1px 0 rgb(0, 0, 0);
      padding: 10px;
      animation: glitch-1 1s infinite;
    }
  
    .glitch:after {
      left: -2px;
      font-family: 'Bruno Ace', sans-serif;
      padding: 10px;
      text-shadow: 1px 0 rgb(0, 0, 0);
      animation: glitch-2 1s infinite;
    }
  
    @keyframes glitch {
      0% {
        clip-path: inset(0 0 0 0);
      }
      20% {
        clip-path: inset(20% 0 30% 0);
      }
      40% {
        clip-path: inset(40% 0 20% 0);
      }
      60% {
        clip-path: inset(30% 0 10% 0);
      }
      80% {
        clip-path: inset(10% 0 20% 0);
      }
      100% {
        clip-path: inset(0 0 0 0);
      }
    }
  
    @keyframes glitch-1 {
      0% {
        transform: translate(0, 0);
      }
      20% {
        transform: translate(-2px, -2px);
      }
      40% {
        transform: translate(2px, 2px);
      }
      60% {
        transform: translate(-2px, -2px);
      }
      80% {
        transform: translate(2px, 2px);
      }
      100% {
        transform: translate(0, 0);
      }
    }
  
    @keyframes glitch-2 {
      0% {
        transform: translate(0, 0);
      }
      20% {
        transform: translate(2px, 2px);
      }
      40% {
        transform: translate(-2px, -2px);
      }
      60% {
        transform: translate(2px, 2px);
      }
      80% {
        transform: translate(-2px, -2px);
      }
      100% {
        transform: translate(0, 0);
      }
    }
  </style>

<div class="hero-card ">
    <div class="pt-40 pr-10  flex  items-center bg-white  rounded-lg  md:flex-col md:max-w-xl dark:border-gray-700 dark:bg-gray-800 dark:hover:bg-gray-700">
        <h3 class="mb-2 text-6xl font-bold tracking-tight text-gray-900 dark:text-white">Project Impulse is </h3>
        <br>
        <div class="glitch" data-text={words[currentIndex]}>
            {words[currentIndex]}
        </div>
    </div>   
    <img src="/images/pi-construction-bg.png" alt="Project Impulse" class="ml-4 w-3/5" />
</div>

  