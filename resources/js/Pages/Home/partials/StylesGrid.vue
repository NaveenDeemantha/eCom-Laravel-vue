<template>
    <section class="image-grid">
        <div class="section-wrapper">
            <div class="container">
                <div class="row">
                    <!-- Text Content Container -->
                    <div class="container-left">
                        <div class="content-container">
                            <div class="content-box">
                                <h1 class="heading">Shop With Us</h1>
                                <p class="subtitle">
                                    We're looking for incredible people to build on our strong momentum. Help us power the brands you
                                    know and love.
                                </p>
                                <a href="#position" class="btn btn-primary">See all Categories</a>
                            </div>
                        </div>
                    </div>

                    <!-- Image Grid Container -->
                    <div class="container-right">
                        <div class="images-container">
                            <div class="image-grid-container">
                              <marquee behaviour="scroll" direction="up" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs.webp" alt="Grid Image 1" class="grid-image">
                                </div>
                              </marquee> 
                              <marquee behaviour="scroll" direction="down" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs2.webp" alt="Grid Image 2" class="grid-image">
                                </div>
                              </marquee>   
                              <marquee behaviour="scroll" direction="up">
                                <div class="image-grid-item">
                                    <img src="/images/imgs3.webp" alt="Grid Image 3" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="down" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs4.webp" alt="Grid Image 4" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="up">
                                <div class="image-grid-item">
                                    <img src="/images/imgs5.webp" alt="Grid Image 5" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="down" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs6.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="up">
                                <div class="image-grid-item">
                                    <img src="/images/imgs7.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="down" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs8.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="up">
                                <div class="image-grid-item">
                                    <img src="/images/imgs9.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="down" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs10.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="up">
                                <div class="image-grid-item">
                                    <img src="/images/imgs11.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                              <marquee behaviour="scroll" direction="down" >
                                <div class="image-grid-item">
                                    <img src="/images/imgs12.webp" alt="Grid Image 6" class="grid-image">
                                </div>
                              </marquee>  
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>

.image-grid {
  padding: 0.5rem 1.5rem;
  background-color: rgba(255, 255, 255, 0.9);
}

.section-wrapper {
  max-width: 1200px;
  margin: 0 auto;
}

.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 0.5rem;
}


/* Set specific widths */
.container-left {
  flex: 0 0 30%;
  max-width: 30%;
}

.container-right {
  flex: 0 0 70%;
  max-width: 70%;
}

.container-left,
.container-right {
  flex: 1 1 48%;
  box-sizing: border-box;
  padding: 0.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.content-container {
  width: 100%;
}

.content-box {
  width: 100%;
  max-width: 420px;
  text-align: center;
  background-color: rgba(255, 255, 255, 0.9);
  padding: 1.5rem;
}

.heading {
  font-family: 'roboto', sans-serif;
  font-size: 1.75rem;
  font-weight: bold;
  margin-bottom: 0.75rem;
}

.subtitle {
  font-size: 0.95rem;
  color: #555;
  margin-bottom: 1.25rem;
  font-family: 'roboto', sans-serif;
}

.btn-primary {
  display: inline-block;
  padding: 0.6rem 1.2rem;
  background-color: #000000;
  color: white;
  text-decoration: none;
  border-radius: 6px;
  font-size: 0.95rem;
  transition: background 0.3s ease;
}

.btn-primary:hover {
  background-color: #ffffff;
  color: #000000;
  border: 1px solid #000000;
}



/* Image grid */
.images-container {
  width: 100%;
  height: 100%;
}

.image-grid-container {
  display: grid;
  width: 120%;
  height: 500px;
  grid-template-columns: repeat(6, 1fr);
  gap: 8px;
}

.grid-image {
  width: 120%;
  height: 100%;
  border-radius: 6px;
  object-fit: cover;
}

.image-grid-item {
  overflow: hidden;
  border-radius: 6px;
}
</style>

<script>

</script>