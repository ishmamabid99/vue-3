<!-- Footer.vue -->
<template>
  <footer class="footer" :style="{ backgroundColor: '#4682c0' }">
    <div class="footer-content">
      <div class="social-media">
        <a href="https://www.facebook.com/" target="_blank">
          <img src="facebook_logo.png" alt="Facebook" />
        </a>
        <a href="https://twitter.com/" target="_blank">
          <img src="twitter_logo.png" alt="Twitter" />
        </a>
        <a
          href="https://api.whatsapp.com/send?phone=1234567890"
          target="_blank"
        >
          <img src="whatsapp_logo.png" alt="WhatsApp" />
        </a>
        <a href="https://www.instagram.com/" target="_blank">
          <img src="instagram_logo.png" alt="Instagram" />
        </a>
      </div>
      <div class="contact-info">
        <p>Contacts:</p>
        <p>Sales: sales@example.com</p>
        <p>Support: support@example.com</p>
        <!-- Add other contact information here -->
      </div>
    </div>
  </footer>
</template>
<script>
export default {};
</script>

<style>
/* Add your custom styles for the footer here */
.footer {
  position: fixed;
  bottom: 0;
  padding: 20px;
  color: white;
  width: 100%;
  min-width: 100vw;
}

.footer-content {
  display: flex;
  justify-content: space-between;
}

.social-media img {
  width: 30px;
  height: 30px;
  margin-right: 10px;
}

.contact-info p {
  margin: 0;
}
</style>
