DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GiiiT | Cinematic Story Hub</title>
    <style>
        :root {
            --gold: #d4af37;
            --dark-bg: #050505;
            --card-bg: #111111;
            --accent: #1a1a1a;
            --text-main: #ffffff;
            --text-dim: #999999;
        }

        body {
            font-family: 'Inter', 'Segoe UI', Roboto, sans-serif;
            background-color: var(--dark-bg);
            color: var(--text-main);
            margin: 0;
            scroll-behavior: smooth;
        }

        /* Cinematic Header */
        header {
            text-align: center;
            padding: 100px 20px 60px;
            background: radial-gradient(circle at center, #1a1a1a 0%, #050505 100%);
        }

        .main-brand {
            font-size: clamp(3rem, 10vw, 6rem);
            font-weight: 800;
            letter-spacing: 20px;
            margin: 0;
            color: var(--gold);
            text-transform: uppercase;
            text-shadow: 0 0 20px rgba(212, 175, 55, 0.3);
        }

        .sub-brands {
            margin-top: 30px;
            font-size: 0.8rem;
            color: var(--text-dim);
            letter-spacing: 3px;
            text-transform: uppercase;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
        }

        .sub-brands span { border: 1px solid #333; padding: 5px 15px; border-radius: 20px; }

        .container { max-width: 1100px; margin: 0 auto; padding: 40px 20px; }

        /* Story Form */
        .story-form {
            background: var(--card-bg);
            padding: 40px;
            border-radius: 12px;
            border: 1px solid #222;
            margin-bottom: 80px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        h2 { font-weight: 300; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 25px; color: var(--gold); }

        input, textarea {
            width: 100%;
            background: #000;
            border: 1px solid #333;
            color: white;
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 15px;
            font-size: 1rem;
        }

        .submit-btn {
            background: var(--gold);
            color: black;
            padding: 15px 40px;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: 0.4s ease;
        }

        .submit-btn:hover { background: #fff; transform: scale(1.02); }

        /* Feed */
        .story-feed {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 25px;
        }

        .story-card {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 10px;
            border-bottom: 3px solid transparent;
            transition: 0.3s;
            animation: fadeIn 0.5s ease;
        }

        .story-card:hover { border-bottom: 3px solid var(--gold); background: #161616; }

        .story-card h3 { margin: 0 0 10px; font-size: 1.2rem; color: #fff; }
        .story-card p { font-size: 0.95rem; color: var(--text-dim); height: 80px; overflow: hidden; }
        .story-card .author { font-size: 0.75rem; color: var(--gold); text-transform: uppercase; letter-spacing: 1px; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* Insta Section */
        .insta-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 30px;
        }

        .insta-placeholder {
            aspect-ratio: 1/1;
            background: #1a1a1a;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 5px;
            overflow: hidden;
            border: 1px solid #222;
        }

        .insta-placeholder img { width: 100%; height: 100%; object-fit: cover; opacity: 0.7; }
    </style>
</head>
<body>

<header>
    <h1 class="main-brand">GiiiT</h1>
    <div class="sub-brands">
        <span>Gitartha Deka Films</span>
        <span>Giiitartha</span>
        <span>SONIT MUSIC</span>
        <span>Brotherswood Production</span>
    </div>
</header>

<div class="container">
    
    <section class="story-form">
        <h2>Submit Your Vision</h2>
        <input type="text" id="storyTitle" placeholder="Story Title">
        <input type="text" id="userName" placeholder="Your Name">
        <textarea id="storyContent" placeholder="Tell your story... We might turn it into a Gitartha Deka Films production."></textarea>
        <button class="submit-btn" onclick="postStory()">Post Story</button>
    </section>

    <section>
        <h2>Community Stories</h2>
        <div class="story-feed" id="feed">
            <div class="story-card">
                <h3>The Neon Silence</h3>
                <p>A story about a man who can only hear colors in the streets of Guwahati.</p>
                <div class="author">By Gitartha</div>
            </div>
        </div>
    </section>

    <section style="margin-top: 100px; text-align: center;">
        <h2>Visual Works</h2>
        <div class="insta-grid">
            <div class="insta-placeholder">
                <img src="...">
            </div>
            <div class="insta-placeholder">
                <img src=giiitfilms.jpg/400x400/111/gold?text=Production" alt="Film">
            </div>
            <div class="insta-placeholder">
                <img src="https://via.placeholder.com/400x400/111/gold?text=Behind+The+Scenes" alt="BTS">
            </div>
        </div>
        <p style="margin-top: 20px; color: var(--text-dim);">Follow <a href="https://instagram.com/being_giiit" style="color: var(--gold);">@being_giiit</a> & <a href="https://instagram.com/gitartha_deka_films" style="color: var(--gold);">@gitartha_deka_films</a></p>
    </section>

</div>

<script>
    function postStory() {
        const title = document.getElementById('storyTitle').value;
        const name = document.getElementById('userName').value;
        const content = document.getElementById('storyContent').value;

        if(!title || !name || !content) {
            alert("Please fill in all fields to submit.");
            return;
        }

        const feed = document.getElementById('feed');
        
        // Create the new story card
        const card = document.createElement('div');
        card.className = 'story-card';
        card.innerHTML = `
            <h3>${title}</h3>
            <p>${content}</p>
            <div class="author">By ${name}</div>
        `;

        // Add to the top of the feed
        feed.prepend(card);

        // Clear inputs
        document.getElementById('storyTitle').value = '';
        document.getElementById('userName').value = '';
        document.getElementById('storyContent').value = '';

        alert("Story posted to the community feed!");
    }
</script>

</body>
</html>

