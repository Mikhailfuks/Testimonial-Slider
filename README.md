<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Testimonial Slider</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        .testimonial-slider {
            width: 80%;
            margin: 50px auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .testimonial-card {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .testimonial-text {
            flex: 1;
            padding: 20px;
            border-radius: 10px;
            background-color: #f9f9f9;
            margin-right: 20px;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
        }

        .testimonial-author img {
            width: 60px;
            height: 60px;
            border-radius: 50%;
        }

        .testimonial-author .author-info {
            margin-left: 15px;
        }

        .testimonial-author .author-name {
            font-weight: bold;
            font-size: 18px;
        }

        .testimonial-author .author-title {
            color: #888;
        }

        .slider-controls {
            display: flex;
            justify-content: center;
        }

        .slider-controls button {
            background-color: #ddd;
            border: none;
            border-radius: 50%;
            padding: 10px;
            margin: 0 10px;
            cursor: pointer;
        }

        .slider-controls button:hover {
            background-color: #ccc;
        }
    </style>
</head>
<body>

    <div class="testimonial-slider">
        <div class="testimonial-card">
            <div class="testimonial-text">
                <p>"This product is amazing! It's exceeded my expectations and has made my life so much easier." </p>
            </div>
            <div class="testimonial-author">
                <img src="https://via.placeholder.com/60" alt="Testimonial Author">
                <div class="author-info">
                    <div class="author-name">John Doe</div>
                    <div class="author-title">Happy Customer</div>
                </div>
            </div>
        </div>



        <div class="testimonial-card">
            <div class="testimonial-text">
                <p>"I highly recommend this service. It's reliable, efficient, and the customer support is fantastic." </p>
            </div>
            <div class="testimonial-author">
                <img src="https://via.placeholder.com/60" alt="Testimonial Author">
                <div class="author-info">
                    <div class="author-name">Jane Smith</div>
                    <div class="author-title">Satisfied User</div>
                </div>
            </div>
        </div>

        <div class="slider-controls">
            <button class="prev">Previous</button>
            <button class="next">Next</button>
        </div>
    </div>

    <script>
        const testimonialCards = document.querySelectorAll('.testimonial-card');
        const prevButton = document.querySelector('.prev');
        const nextButton = document.querySelector('.next');
        let currentCard = 0;

        function showTestimonial(index) {
            testimonialCards.forEach((card, i) => {
                card.style.display = i === index ? 'flex' : 'none';
            });
        }

        function nextTestimonial() {
            currentCard = (currentCard + 1) % testimonialCards.length;
            showTestimonial(currentCard);
        }

        function prevTestimonial() {
            currentCard = (currentCard - 1 + testimonialCards.length) % testimonialCards.length;
            showTestimonial(currentCard);
        }

        nextButton.addEventListener('click', nextTestimonial);
        prevButton.addEventListener('click', prevTestimonial);

        // Initial display
        showTestimonial(currentCard); 
    </script>

</body>
</html>
