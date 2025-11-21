<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VLO225 | Defense Data Intelligence</title>
    <style>
        /* Global Styles - Warm & Formal Theme */
        :root {
            --bg-color: #f4f1ea; /* Warm "Paper" Beige */
            --card-bg: #ffffff;
            --text-primary: #2c2926; /* Warm Charcoal */
            --text-secondary: #595550;
            --accent: #8c3b2b; /* Muted Military Red */
            --border: #dcd6cc;
        }

        body {
            /* Georgia/Serif fonts are the standard for "Formal" analysis */
            font-family: Georgia, "Times New Roman", serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        /* Layout Container */
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Header Section */
        header {
            text-align: center;
            padding-bottom: 40px;
            border-bottom: 2px solid var(--accent);
            margin-bottom: 50px;
        }

        h1 {
            margin: 0;
            font-size: 2.8rem;
            letter-spacing: -0.5px;
            color: #1a1a1a;
        }

        .subtitle {
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif; /* Sans-serif contrast for subtitle */
            color: var(--text-secondary);
            text-transform: uppercase;
            letter-spacing: 1.5px;
            font-size: 0.85rem;
            margin-top: 15px;
            font-weight: 600;
        }

        /* Social Link - Button Style */
        .social-link {
            display: inline-block;
            margin-top: 20px;
            color: var(--text-primary);
            text-decoration: none;
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
            font-size: 0.8rem;
            border: 1px solid #b0aaa0;
            padding: 8px 16px;
            border-radius: 4px;
            transition: all 0.2s ease;
        }

        .social-link:hover {
            background-color: #e6e2d8;
            border-color: var(--text-primary);
        }

        /* Chart Cards */
        .chart-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border);
            margin-bottom: 60px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05); /* Very subtle shadow */
        }

        .chart-info {
            padding: 30px 30px 20px 30px;
            border-bottom: 1px solid var(--bg-color);
        }

        .chart-title {
            font-size: 1.4rem;
            margin: 0 0 10px 0;
        }

        .chart-desc {
            color: var(--text-secondary);
            font-size: 1rem;
            margin: 0;
            font-style: italic;
        }

        /* Image Handling - Thumbnail Style */
        .chart-display {
            padding: 20px;
            background-color: #faf9f7;
            text-align: center;
            cursor: pointer; /* Shows hand icon on hover */
        }

        .chart-display img {
            max-width: 100%;
            max-height: 350px; /* Keeps charts relatively small */
            width: auto;
            display: inline-block;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.2s ease;
        }

        .chart-display:hover img {
            transform: scale(1.02); /* Subtle zoom on hover */
        }
        
        .click-hint {
            font-family: "Helvetica Neue", sans
