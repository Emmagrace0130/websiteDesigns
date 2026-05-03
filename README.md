<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #3b3b3b;
    --surface: #2a2520;
    --primary-dark: #675647;
    --primary-warm: #e3bd98;
    --neutral-tan: #dfd3b5;
    --neutral-gray: #c0bdbc;
    --accent: #6c6e36;
    --text-color: #f5f0e8;
    --text-dim: rgba(245, 240, 232, 0.5);
    --text-faint: rgba(245, 240, 232, 0.2);
    --border: rgba(245, 240, 232, 0.1);
    --border-mid: rgba(245, 240, 232, 0.22);
  }

  html, body {
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: var(--bg);
    font-family: 'Nunito Sans', 'Gill Sans', 'Century Gothic', sans-serif;
  }

  .pf {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    color: var(--text-color);
    letter-spacing: 0.01em;
  }

  .pf-slide {
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 0.9s ease;
    pointer-events: none;
  }
  .pf-slide.active { opacity: 1; pointer-events: all; }

  .pf-bg {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    transition: transform 10s ease;
  }
  .pf-slide.active .pf-bg { transform: scale(1.03); }

  .pf-scrim {
    position: absolute;
    inset: 0;
    background: linear-gradient(to top, rgba(40,33,28,0.94) 0%, rgba(40,33,28,0.25) 55%, rgba(40,33,28,0.5) 100%);
  }

  .pf-top {
    position: absolute;
    top: 0; left: 0; right: 0;
    padding: 1.8rem 2.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 20;
  }

  .pf-logo {
    font-weight: 700;
    font-size: 1rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--neutral-tan);
  }

  .pf-topnav { display: flex; gap: 2.2rem; }
  .pf-topnav a {
    color: var(--text-dim);
    font-size: 0.63rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    text-decoration: none;
    font-weight: 600;
    transition: color 0.2s;
  }
  .pf-topnav a:hover { color: var(--neutral-tan); }

  .pf-bottom {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    padding: 2.5rem 2.5rem 2.2rem;
    z-index: 20;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
    gap: 1rem;
  }

  .pf-info { flex: 1; min-width: 0; }

  .pf-counter {
    font-size: 0.6rem;
    letter-spacing: 0.25em;
    color: var(--primary-warm);
    margin-bottom: 0.7rem;
    font-weight: 700;
    text-transform: uppercase;
  }

  .pf-title {
    font-weight: 800;
    font-size: clamp(1.8rem, 4vw, 3rem);
    line-height: 1.08;
    color: var(--text-color);
    margin-bottom: 0.6rem;
    cursor: pointer;
    display: inline-block;
    transition: color 0.2s;
  }
  .pf-title:hover { color: var(
