<!-- +layout.svelte -->
<script>
    // Any global scripts can be added here
  </script>
  
  <style>
    :global(body) {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #fff;
      color: #000;
      text-align: center;
    }
    header {
      background-color: #141414;
      padding: 20px;
      color: #ffcc00;
    }
    :global(html) {
    scroll-behavior: smooth;
    }
    h1 {
      margin: 0;
      font-size: 36px;
    }
    nav {
      background-color: #222;
      padding: 10px 0;
    }
    nav a {
      color: #ffcc00;
      text-decoration: none;
      margin: 0 15px;
      font-size: 18px;
    }
    nav a:hover {
      text-decoration: underline;
    }
    footer {
      background-color: #141414;
      padding: 10px;
      margin-top: 20px;
      color: #ffcc00;
    }
  </style>
  
  <header>
    <h1>Central Florida Kendobu</h1>
    <p>Motto goes here</p>
  </header>
  
  <nav>
    <a href="#about" class="cta-button">About</a>
    <a href="#cabinet">Cabinet</a>
    <a href="#practice">Practice</a>
    <a href="#contact">Contact</a>
  </nav>
  
  <slot></slot>
  
  <footer>
    <p>&copy; 2025 Central Florida Kendobu | <a href="mailto:cfkendo@gmail.com" style="color: #ffcc00;">Contact Us</a></p>
  </footer>