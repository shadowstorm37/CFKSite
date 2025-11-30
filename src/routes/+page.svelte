<!-- +page.svelte -->
<script lang="ts">
    /**
     * Replace the images in here to change the slideshow.
     * Additionally, more can be added by extending the string
     */
    let images: string[] = [
      "resources/kendo1.jpg",
      "resources/kendo2.jpg",
      "resources/kendo3.jpg"
    ];
    let currentIndex: number = 0;
    let interval: number;
  
    function prevImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
    }
  
    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
    }
  
    function startSlideshow() {
      interval = setInterval(() => {
        nextImage();
      }, 10000);
    }
  
    startSlideshow();
    import emailjs from 'emailjs-com';
    
    // Form data
    let firstName = '';
    let lastName = '';
    let email = '';
    let subject = '';
    let message = '';
    
    // Error and success state
    let errorMessage = '';
    let successMessage = '';

    const handleSubmit = async (event: Event) => {
        event.preventDefault();

        // Clear any previous messages
        errorMessage = '';
        successMessage = '';

        // Validate form fields
        if (!firstName || !lastName || !email || !subject || !message) {
            errorMessage = 'All fields are required.';
            return;
        }

        try {
            const result = await emailjs.sendForm(
                'service_id', // replace with your EmailJS service ID
                'template_id', // replace with your EmailJS template ID
                event.target as HTMLFormElement,
                'user_id' // replace with your EmailJS user ID
            );
            successMessage = 'Your message has been sent successfully!';
            // Optionally, clear the form here
            firstName = '';
            lastName = '';
            email = '';
            subject = '';
            message = '';
        } catch (error) {
            errorMessage = 'There was an error sending your message. Please try again later.';
        }
    };
</script>
  
  <style>
    .info-section {
      background-color: #001f3f;
      padding: 40px 20px;
      display: flex;
      justify-content: center;
    }
    .info-box {
      background-color: #fff;
      padding: 20px;
      border-radius: 8px;
      max-width: 800px;
      text-align: left;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .cabinet-section {
      background-color: #fff;
      padding: 40px 20px;
    }
    .cabinet-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      max-width: 900px;
      margin: 0 auto;
    }
    .cabinet-member {
      width: 200px;
      background-color: #f4f4f4;
      padding: 10px;
      border-radius: 8px;
      text-align: center;
    }
    .cabinet-member img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 8px;
    }
    .cabinet-title {
      font-weight: bold;
      margin-top: 10px;
    }
    .cabinet-name {
      font-size: 14px;
      color: #333;
    }
    .cabinet-rank {
      font-size: 14px;
      color: #333;
    }
    .cta-button {
      display: inline-block;
      background-color: #ffcc00;
      color: #000;
      padding: 10px 20px;
      text-decoration: none;
      font-weight: bold;
      border-radius: 5px;
    }
    .cta-button:hover {
      background-color: #e6b800;
    }
  
    /* Section styles for slideshow*/
    .slideshow-section {
      background-color: #ffcc00;
      padding: 40px 20px;
    }
    .slideshow-container {
      display: flex;
      justify-content: center;
      gap: 20px;
    }
    .info-box-white {
      background-color: #fff;
      padding: 20px;
      border-radius: 8px;
      width: 45%;
      text-align: left;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .slideshow-box {
      background-color: #fff;
      padding: 20px;
      border-radius: 8px;
      width: 55%;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .slideshow-img {
      width: 100%;
      height: 300px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 10px;
    }
    .slideshow-section {
    background-color: #ffcc00;
    padding: 40px 20px;
    text-align: center;
  }
  .slideshow-container {
    position: relative;
    width: 55%;
    margin: 0 auto;
  }
  .slideshow-box {
    position: relative;
  }
  .slideshow-img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 8px;
  }
  .prev-button, .next-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    font-size: 18px;
    border-radius: 50%;
  }
  .prev-button { left: 10px; }
  .next-button { right: 10px; }
  .prev-button:hover, .next-button:hover {
    background-color: rgba(0, 0, 0, 0.8);
  }

  /* Section styles for contact*/
  .contact-section {
    background-color: #001f3f; /* Navy Blue background */
    color: #fff; /* White text for contrast */
    padding: 40px 20px;
    text-align: center;
  }

  .contact-form {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    max-width: 600px;
    margin: 0 auto;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  .contact-form input, .contact-form textarea {
    width: 100%;
    padding: 12px;
    margin: 10px 0;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 16px;
  }

  .contact-form button {
    background-color: #ffcc00;
    color: #000;
    padding: 12px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
  }

  .contact-form button:hover {
    background-color: #e6b800;
  }

  .message {
    margin-top: 20px;
    font-weight: bold;
  }

  .error {
    color: red;
  }

  .success {
    color: green;
  }
  </style>
  
  <section id="about" class="info-section">
    <div class="info-box">
      <h2>About Central Florida Kendobu</h2>
      <p>Central Florida Kendobu was created in 2007 to introduce Kendo to the students of the University of Central Florida. We strive to make an environment where anyone can learn Kendo regardless of experience.</p>
        <p>Kendo, meaning "Way of The Sword", is a modern Japanese martial art of sword-fighting based on traditional samurai swordsmanship, or kenjutsu. Kendo is a physically and mentally challenging activity that 
        combines strong martial arts values with sport-like physical elements.
      </p>
    </div>
  </section>
  
  <!--
    Switch Cabinet Members in here when Officer Changes happen. Files need to be in static/resources
    Additionally, If ranks are/are not present, you can delete or add the field as necessary
  -->
  <section id="cabinet" class="cabinet-section">
    <h2>Cabinet</h2>
    <div class="cabinet-container">
      <div class="cabinet-member">
        <img src="resources/president.jpg" alt="President">
        <div class="cabinet-title">President</div>
        <div class="cabinet-name">James Barnett</div>
        <div class="cabinet-rank">1 Dan</div>
      </div>
      <div class="cabinet-member">
        <img src="resources/vicepresident.jpg" alt="Vice-President">
        <div class="cabinet-title">Vice-President</div>
        <div class="cabinet-name">Matthew Barton</div>
      </div>
      <div class="cabinet-member">
        <img src="resources/treasurer.jpg" alt="Treasurer">
        <div class="cabinet-title">Treasurer</div>
        <div class="cabinet-name">William Davis</div>
      </div>
      <div class="cabinet-member">
        <img src="resources/riskmanager.jpg" alt="Risk Manager">
        <div class="cabinet-title">Risk Manager</div>
        <div class="cabinet-name">Ivan Pham</div>
      </div>
      <div class="cabinet-member">
        <img src="resources/secretary.jpg" alt="Secretary">
        <div class="cabinet-title">Secretary</div>
        <div class="cabinet-name">Vanessa Junco</div>
      </div>
      <div class="cabinet-member">
        <img src="resources/creativemanager.jpg" alt="Creative Manager">
        <div class="cabinet-title">Creative Manager</div>
        <div class="cabinet-name">Zuzanny Warren</div>
      </div>
    </div>
  </section>
  
  <!-- Section for Information and Slideshow -->
  <section id="practice" class="slideshow-section">
    <div class="slideshow-container">
      <!-- Information Box (Stays Static) -->
      <div class="info-box-white">
        <h3>Information</h3>
        <p>Practice Dates are every Tuesday and Thursday from 9:30-11:30pm located in the Group Exercise Room II</p>
        <p>Stay tuned for more events and announcements. We look forward to seeing you on the mat!</p>
      </div>
  
      <!-- Slideshow Box (With Controls) -->
      <div class="slideshow-box">
        <button class="prev-button" on:click={prevImage}>&#10094;</button>
        <img src={images[currentIndex]} class="slideshow-img" alt="Slideshow Image">
        <button class="next-button" on:click={nextImage}>&#10095;</button>
      </div>
    </div>
</section>
    <!-- Contact Form Section -->
<section id="contact" class="contact-section">
    <h2>Contact Us</h2>
    <p>If you have any questions or would like to get in touch, feel free to send us a message!</p>
  
    <form class="contact-form" on:submit={handleSubmit}>
      <input type="text" name="first_name" placeholder="First Name" bind:value={firstName} required />
      <input type="text" name="last_name" placeholder="Last Name" bind:value={lastName} required />
      <input type="email" name="user_email" placeholder="Email" bind:value={email} required />
      <input type="text" name="subject" placeholder="Subject" bind:value={subject} required />
      <textarea name="message" placeholder="Your Message" rows="5" bind:value={message} required></textarea>
      <button type="submit">Submit</button>
    </form>
  
    {#if errorMessage}
      <div class="message error">{errorMessage}</div>
    {/if}
  
    {#if successMessage}
      <div class="message success">{successMessage}</div>
    {/if}
  </section>