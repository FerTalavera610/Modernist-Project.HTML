<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Four Doors of the Mind</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: Georgia, serif;
}

body{
    background: linear-gradient(to bottom, #0f172a, #1e1b4b);
    color:white;
    min-height:100vh;
    overflow-x:hidden;
}

.screen{
    display:none;
    min-height:100vh;
    padding:40px 20px;
    text-align:center;
}

.active{
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
}

h1{
    margin-bottom:10px;
    font-size:3rem;
}

.subtitle{
    opacity:.8;
    margin-bottom:50px;
}

.doors{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:30px;
    max-width:800px;
    width:100%;
}

.door{
    background:rgba(255,255,255,0.08);
    border:2px solid rgba(255,255,255,0.2);
    border-radius:15px;
    padding:40px;
    cursor:pointer;
    transition:.3s;
}

.door:hover{
    transform:scale(1.05);
    box-shadow:0 0 25px rgba(255,255,255,.3);
}

.door-icon{
    font-size:3rem;
    margin-bottom:10px;
}

.description{
    margin-top:10px;
    opacity:.8;
}

.poem-page{
    max-width:700px;
    margin:auto;
}

.poem-page h2{
    margin-bottom:20px;
    font-size:2.5rem;
}

.poem{
    line-height:2;
    font-size:1.1rem;
    white-space:pre-line;
}

button{
    margin-top:40px;
    padding:12px 25px;
    border:none;
    border-radius:10px;
    cursor:pointer;
    background:#4338ca;
    color:white;
    font-size:1rem;
}

button:hover{
    background:#6366f1;
}

.secret-door{
    margin-top:50px;
    cursor:pointer;
    opacity:.7;
    transition:.3s;
    font-size:.9rem;
}

.secret-door:hover{
    opacity:1;
}

.particles{
    position:fixed;
    width:100%;
    height:100%;
    pointer-events:none;
    z-index:-1;
}

.particle{
    position:absolute;
    width:4px;
    height:4px;
    background:white;
    border-radius:50%;
    opacity:.4;
    animation:float 10s linear infinite;
}

@keyframes float{
    from{
        transform:translateY(100vh);
    }
    to{
        transform:translateY(-100px);
    }
}

@media(max-width:600px){
    .doors{
        grid-template-columns:1fr;
    }

    h1{
        font-size:2rem;
    }
}
</style>
</head>
<body>

<div class="particles" id="particles"></div>

<!-- HOME -->
<div id="home" class="screen active">
    <h1>The Four Doors of the Mind</h1>
    <p class="subtitle">Choose a door and explore what lies beneath the surface.</p>

    <div class="doors">

        <div class="door" onclick="showPage('memory')">
            <div class="door-icon">🗝️</div>
            <h3>Memory</h3>
            <p class="description">Forgotten moments from the past.</p>
        </div>

        <div class="door" onclick="showPage('dream')">
            <div class="door-icon">🌙</div>
            <h3>Dream</h3>
            <p class="description">Strange places and impossible ideas.</p>
        </div>

        <div class="door" onclick="showPage('shadow')">
            <div class="door-icon">🕳️</div>
            <h3>Shadow</h3>
            <p class="description">Hidden fears and worries.</p>
        </div>

        <div class="door" onclick="showPage('mask')">
            <div class="door-icon">🎭</div>
            <h3>Mask</h3>
            <p class="description">The difference between who we are and who people see.</p>
        </div>

    </div>

    <div class="secret-door" onclick="showPage('about')">
        🚪 The Voices Behind the Words
    </div>
</div>

<!-- MEMORY -->
<div id="memory" class="screen">
    <div class="poem-page">
        <h2>Old Pictures</h2>

        <div class="poem">
I found an old picture on a shelf.
It made me think about the past.

I remembered people, places, and days
that I had almost forgotten.

The picture stayed in my hand,
but the memories felt far away,
like they were hiding somewhere
inside my mind.
        </div>

        <button onclick="goHome()">Return Home</button>
    </div>
</div>

<!-- DREAM -->
<div id="dream" class="screen">
    <div class="poem-page">
        <h2>Last Night</h2>

        <div class="poem">
Last night I had a strange dream.

I was walking through the clouds
and the stars were close enough to touch.

Nothing made sense,
but somehow it felt normal.

When I woke up,
most of it disappeared,
but I still remember
how it felt.
        </div>

        <button onclick="goHome()">Return Home</button>
    </div>
</div>

<!-- SHADOW -->
<div id="shadow" class="screen">
    <div class="poem-page">
        <h2>The Dark Corner</h2>

        <div class="poem">
Sometimes I keep my worries
in a dark corner of my mind.

I try not to think about them,
but they do not completely leave.

They stay quiet in the background,
waiting for me to notice them.

Even though they can be scary,
they are still a part of me.
        </div>

        <button onclick="goHome()">Return Home</button>
    </div>
</div>

<!-- MASK -->
<div id="mask" class="screen">
    <div class="poem-page">
        <h2>Who I Am</h2>

        <div class="poem">
At school I act one way.
At home I act another.

People see what I choose to show,
but they do not see every thought I have.

There is the person everyone knows,
and the person only I know.

Both of them are me.
        </div>

        <button onclick="goHome()">Return Home</button>
    </div>
</div>

<!-- ABOUT -->
<div id="about" class="screen">
    <div class="poem-page">
        <h2>About These Poems</h2>

        <div class="poem">
These poems were written for this project.

They represent four parts of the subconscious mind:

• Memory → things from the past.

• Dream → imagination and strange thoughts.

• Shadow → fears and worries.

• Mask → identity and how we present ourselves to others.

The website is based on Modernist ideas because visitors must explore the doors to discover different thoughts and feelings hidden inside the mind.
        </div>

        <button onclick="goHome()">Return Home</button>
    </div>
</div>

<script>
function showPage(page){
    document.querySelectorAll(".screen")
        .forEach(screen => screen.classList.remove("active"));

    document.getElementById(page)
        .classList.add("active");
}

function goHome(){
    showPage("home");
}

// particles
const particlesContainer = document.getElementById("particles");

for(let i = 0; i < 40; i++){
    const particle = document.createElement("div");
    particle.classList.add("particle");

    particle.style.left = Math.random() * 100 + "%";
    particle.style.animationDuration =
        (5 + Math.random() * 10) + "s";

    particle.style.animationDelay =
        Math.random() * 10 + "s";

    particlesContainer.appendChild(particle);
}
</script>

</body>
</html>