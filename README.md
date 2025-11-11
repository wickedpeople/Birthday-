# Birthday-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>You're Invited! Birthday Celebration</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Define custom font and smooth transitions */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f7f3f3;
            transition: all 0.3s ease-in-out;
        }
        .confetti-background {
            background-image: radial-gradient(circle at 100% 100%, #ffd700 0%, transparent 10%),
                              radial-gradient(circle at 0% 0%, #ff6347 0%, transparent 15%),
                              radial-gradient(circle at 75% 25%, #4682b4 0%, transparent 8%),
                              radial-gradient(circle at 25% 75%, #32cd32 0%, transparent 12%);
            background-size: 1000px 1000px;
            animation: moveBackground 60s linear infinite alternate;
        }

        @keyframes moveBackground {
            from { background-position: 0% 0%; }
            to { background-position: 100% 100%; }
        }

        .card-shadow {
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15), 0 5px 15px rgba(255, 165, 0, 0.4);
        }

        .rsvp-button {
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .rsvp-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 105, 180, 0.6);
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 md:p-8 confetti-background">

    <!-- Main Content Card -->
    <div id="main-card" class="bg-white rounded-3xl p-6 sm:p-10 max-w-lg w-full card-shadow transition-all duration-500 ease-in-out transform hover:scale-[1.01]">
        
        <!-- Header & Main Message -->
        <header class="text-center mb-8">
            <p class="text-pink-600 font-extrabold text-lg sm:text-xl uppercase tracking-widest animate-pulse">Save the Date!</p>
            <h1 class="text-5xl sm:text-6xl font-black text-gray-800 my-2 leading-tight">
                Jane's <span class="text-indigo-600">30th</span>!
            </h1>
            <p class="text-gray-500 text-base sm:text-lg">Let's celebrate another trip around the sun with good music and great company.</p>
        </header>

        <!-- Countdown Timer -->
        <div class="mb-8">
            <h2 class="text-center text-2xl font-semibold mb-4 text-gray-700">The Countdown Is On!</h2>
            <div id="countdown" class="flex justify-center space-x-2 sm:space-x-4">
                <!-- Countdown elements will be populated by JS -->
            </div>
            <p id="countdown-message" class="text-center text-sm mt-3 text-red-500 hidden"></p>
        </div>

        <!-- Event Details (Grid Layout) -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-10 text-center">
            
            <!-- Date -->
            <div class="bg-blue-50 p-4 rounded-xl shadow-inner border-l-4 border-blue-400">
                <i data-lucide="calendar" class="w-6 h-6 text-blue-500 mx-auto mb-2"></i>
                <p class="font-bold text-gray-800 text-xl">12/01</p>
                <p class="text-sm text-gray-500">Saturday at 7 PM</p>
            </div>

            <!-- Location -->
            <div class="bg-green-50 p-4 rounded-xl shadow-inner border-l-4 border-green-400">
                <i data-lucide="map-pin" class="w-6 h-6 text-green-500 mx-auto mb-2"></i>
                <p class="font-bold text-gray-800 text-xl truncate">The Loft Studio</p>
                <a href="#" class="text-sm text-green-600 hover:text-green-800 underline transition">View Map</a>
            </div>

            <!-- Attire/Theme -->
            <div class="bg-purple-50 p-4 rounded-xl shadow-inner border-l-4 border-purple-400">
                <i data-lucide="t-shirt" class="w-6 h-6 text-purple-500 mx-auto mb-2"></i>
                <p class="font-bold text-gray-800 text-xl">Cocktail Casual</p>
                <p class="text-sm text-gray-500">Dress to impress!</p>
            </div>
        </div>

        <!-- Call to Action (RSVP) -->
        <div class="text-center">
            <button onclick="document.getElementById('rsvp-section').scrollIntoView({ behavior: 'smooth' });"
                class="rsvp-button bg-pink-500 hover:bg-pink-600 text-white font-extrabold py-3 px-8 rounded-full text-xl uppercase tracking-wider shadow-lg hover:shadow-xl transition-all duration-300">
                <i data-lucide="party-popper" class="inline w-5 h-5 mr-2"></i> RSVP Now!
            </button>
        </div>
        
        <!-- Detailed Info/RSVP Form Section -->
        <section id="rsvp-section" class="mt-12 pt-6 border-t border-gray-100">
            <h3 class="text-center text-3xl font-bold text-gray-800 mb-6">Confirm Your Spot</h3>
            <form id="rsvp-form" class="space-y-4">
                <div>
                    <label for="name" class="block text-sm font-medium text-gray-700">Your Full Name</label>
                    <input type="text" id="name" name="name" required
                        class="mt-1 block w-full rounded-lg border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 p-3 border">
                </div>
                <div>
                    <label for="attendance" class="block text-sm font-medium text-gray-700">Will you be attending?</label>
                    <select id="attendance" name="attendance" required
                        class="mt-1 block w-full rounded-lg border-gray-300 shadow-sm focus:border-indigo-500 focus:ring-indigo-500 p-3 border bg-white">
                        <option value="">-- Select an option --</option>
                        <option value="yes">Yes, I'm ready to party!</option>
                        <option value="no">Regretfully, I can't make it.</option>
                    </select>
                </div>
                
                <div class="pt-2">
                    <button type="submit"
                        class="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-semibold py-3 rounded-xl shadow-md transition duration-200">
                        Submit RSVP
                    </button>
                </div>
            </form>
            <p id="response-message" class="text-center mt-4 font-medium hidden"></p>
        </section>

    </div>

    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // --- Countdown Logic ---
        const eventDate = new Date("December 1, 2026 19:00:00").getTime();
        const countdownElement = document.getElementById("countdown");
        const countdownMessage = document.getElementById("countdown-message");

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = eventDate - now;

            // Time calculations for days, hours, minutes and seconds
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            let htmlContent = '';

            if (distance > 0) {
                const parts = [
                    { value: days, label: "Days" },
                    { value: hours, label: "Hours" },
                    { value: minutes, label: "Mins" },
                    { value: seconds, label: "Secs" }
                ];

                parts.forEach(part => {
                    htmlContent += `
                        <div class="flex flex-col items-center bg-gray-100 p-3 rounded-xl min-w-[70px] border border-gray-200">
                            <span class="text-3xl font-extrabold text-pink-500">${part.value.toString().padStart(2, '0')}</span>
                            <span class="text-xs font-medium text-gray-500 uppercase">${part.label}</span>
                        </div>
                    `;
                });
                countdownElement.innerHTML = htmlContent;
            } else {
                // Event is over or starting
                countdownElement.innerHTML = '';
                countdownMessage.textContent = "The party is happening NOW!";
                countdownMessage.classList.remove('hidden');
                clearInterval(timerInterval);
            }
        }

        // Update the count every 1 second
        const timerInterval = setInterval(updateCountdown, 1000);
        updateCountdown(); // Initial call to display immediately

        // --- RSVP Form Handler (Placeholder since no backend/database is connected) ---
        const rsvpForm = document.getElementById("rsvp-form");
        const responseMessage = document.getElementById("response-message");

        rsvpForm.addEventListener("submit", function(event) {
            event.preventDefault();
            const name = document.getElementById("name").value;
            const attendance = document.getElementById("attendance").value;

            // Simulate successful form submission
            responseMessage.classList.remove('hidden', 'text-red-500');
            responseMessage.classList.add('text-green-600');
            responseMessage.innerHTML = `Thanks, <strong>${name}</strong>! Your RSVP (${attendance}) has been received. We can't wait to celebrate!`;
            
            // In a real application, we would use Firebase Firestore here to save the data:
            // saveRSVP({ name, attendance });
            rsvpForm.reset();
        });

    </script>
</body>
</html>

