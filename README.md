<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sri Renga Dental Clinic</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-firestore-compat.js"></script>
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #fbfbfd; color: #1d1d1f; }
        
        .glass-nav { 
            background: rgba(251, 251, 253, 0.8); 
            backdrop-filter: blur(20px); 
            -webkit-backdrop-filter: blur(20px); 
            border-bottom: 1px solid rgba(0,0,0,0.05); 
        }
        
        .card-glass { 
            background: rgba(255, 255, 255, 0.7); 
            backdrop-filter: blur(24px); 
            -webkit-backdrop-filter: blur(24px);
            border: 1px solid rgba(255,255,255,0.5); 
            box-shadow: 0 10px 40px rgba(0,0,0,0.04); 
            border-radius: 24px;
        }

        .input-field { 
            background: rgba(0,0,0,0.02); 
            border: 1px solid rgba(0,0,0,0.08); 
            border-radius: 12px;
            padding: 14px 16px;
            transition: all 0.3s ease; 
            width: 100%;
        }

        .input-field:focus { 
            background: #fff; 
            border-color: #0066cc; 
            box-shadow: 0 0 0 4px rgba(0,102,204,0.1); 
            outline: none; 
        }

        .btn-primary { 
            background: #0066cc; 
            color: white; 
            border-radius: 980px;
            padding: 12px 24px;
            font-weight: 500;
            transition: all 0.3s ease; 
            border: none;
            cursor: pointer;
        }

        .btn-primary:hover { 
            background: #005bb5; 
            transform: scale(0.98); 
        }

        .btn-secondary {
            background: rgba(0,0,0,0.05);
            color: #1d1d1f;
            border-radius: 980px;
            padding: 12px 24px;
            font-weight: 500;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .btn-secondary:hover {
            background: rgba(0,0,0,0.1);
        }

        .time-slot { 
            border: 1px solid #d2d2d7; 
            border-radius: 12px;
            padding: 12px;
            text-align: center;
            color: #1d1d1f; 
            cursor: pointer; 
            transition: all 0.2s ease; 
            font-size: 0.9rem;
            font-weight: 500;
        }

        .time-slot:hover:not(.disabled):not(.selected) { 
            border-color: #86868b; 
        }

        .time-slot.selected { 
            background: #0066cc; 
            color: #fff; 
            border-color: #0066cc; 
        }

        .time-slot.disabled { 
            background: #f5f5f7; 
            color: #86868b; 
            cursor: not-allowed; 
            text-decoration: line-through; 
            opacity: 0.5; 
            border-color: #e5e5ea; 
        }

        .fade-in { animation: fadeIn 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
        @keyframes fadeIn { 
            from { opacity: 0; transform: translateY(20px); } 
            to { opacity: 1; transform: translateY(0); } 
        }

        .view-section { display: none; }
        .view-section.active { display: block; }
    </style>
</head>
<body class="antialiased selection:bg-blue-200 selection:text-blue-900">

    <!-- Navigation -->
    <nav class="fixed w-full top-0 z-50 glass-nav transition-all duration-300">
        <div class="max-w-6xl mx-auto px-6 py-4 flex justify-between items-center">
            <div class="text-xl font-semibold tracking-tight cursor-pointer" onclick="navigate('home')">
                Sri Renga <span class="text-blue-600">Dental</span>
            </div>
            <div class="hidden md:flex space-x-8 text-sm font-medium text-gray-600">
                <a href="#services" class="hover:text-blue-600 transition-colors" onclick="navigate('home')">Services</a>
                <a href="#contact" class="hover:text-blue-600 transition-colors" onclick="navigate('home')">Contact</a>
                <button onclick="navigate('booking')" class="text-blue-600 hover:text-blue-800 transition-colors">Book Appointment</button>
            </div>
        </div>
    </nav>

    <!-- MAIN HOME VIEW -->
    <main id="view-home" class="view-section active pt-32 pb-20 fade-in">
        
        <!-- Hero Section -->
        <section class="max-w-6xl mx-auto px-6 text-center mb-32">
            <h1 class="text-5xl md:text-7xl font-bold tracking-tighter mb-6 text-gray-900">
                A brighter smile.<br><span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-cyan-500">Perfected locally.</span>
            </h1>
            <p class="text-xl text-gray-500 max-w-2xl mx-auto mb-10 font-light">
                Led by Dr. E. R. Suresh Kumar, bringing over two decades of comprehensive dental excellence to Rajapalayam.
            </p>
            <div class="flex justify-center gap-4">
                <button onclick="navigate('booking')" class="btn-primary text-lg px-8 py-4">Book a Visit</button>
                <a href="#contact" class="btn-secondary text-lg px-8 py-4 inline-flex items-center justify-center">Contact Clinic</a>
            </div>
        </section>

        <!-- Image / Environment Section (CSS Placeholder for soft aesthetic) -->
        <section class="max-w-5xl mx-auto px-6 mb-32">
            <div class="aspect-video rounded-3xl bg-gradient-to-tr from-blue-50 to-gray-100 flex items-center justify-center shadow-inner overflow-hidden border border-gray-200/50">
                <div class="text-center">
                    <svg class="w-16 h-16 text-blue-300 mx-auto mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z"></path></svg>
                    <p class="text-gray-400 font-medium tracking-wide">State-of-the-Art Dental Environment</p>
                </div>
            </div>
        </section>

        <!-- Services -->
        <section id="services" class="max-w-6xl mx-auto px-6 mb-32">
            <h2 class="text-3xl font-bold tracking-tight text-center mb-12">Comprehensive Dental Care.</h2>
            <div class="grid md:grid-cols-3 gap-8">
                <div class="card-glass p-8 text-center hover:-translate-y-1 transition-transform duration-300">
                    <div class="w-12 h-12 bg-blue-100 text-blue-600 rounded-full flex items-center justify-center mx-auto mb-6 text-xl font-bold">1</div>
                    <h3 class="text-xl font-semibold mb-3">General Dentistry</h3>
                    <p class="text-gray-500 text-sm leading-relaxed">Routine checkups, digital X-rays, and comprehensive oral health maintenance.</p>
                </div>
                <div class="card-glass p-8 text-center hover:-translate-y-1 transition-transform duration-300">
                    <div class="w-12 h-12 bg-blue-100 text-blue-600 rounded-full flex items-center justify-center mx-auto mb-6 text-xl font-bold">2</div>
                    <h3 class="text-xl font-semibold mb-3">Advanced Surgeries</h3>
                    <p class="text-gray-500 text-sm leading-relaxed">Painless extractions, root canal treatments, and specialized restorative procedures.</p>
                </div>
                <div class="card-glass p-8 text-center hover:-translate-y-1 transition-transform duration-300">
                    <div class="w-12 h-12 bg-blue-100 text-blue-600 rounded-full flex items-center justify-center mx-auto mb-6 text-xl font-bold">3</div>
                    <h3 class="text-xl font-semibold mb-3">Cosmetic Solutions</h3>
                    <p class="text-gray-500 text-sm leading-relaxed">Professional whitening, precise alignments, and smile correction protocols.</p>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="max-w-4xl mx-auto px-6 mb-20 text-center">
            <h2 class="text-3xl font-bold tracking-tight mb-8">Here when you need us.</h2>
            <div class="card-glass p-10 flex flex-col md:flex-row items-center justify-between gap-8">
                <div class="text-left">
                    <h4 class="text-sm font-semibold text-gray-400 uppercase tracking-wider mb-2">Location</h4>
                    <p class="text-lg font-medium text-gray-900 mb-1">Sri Renga Dental Clinic</p>
                    <p class="text-gray-500">Tenkasi Road Corridor (Near Focus Men's Wear)<br>Rajapalayam, Tamil Nadu</p>
                </div>
                <div class="h-16 w-px bg-gray-200 hidden md:block"></div>
                <div class="text-left">
                    <h4 class="text-sm font-semibold text-gray-400 uppercase tracking-wider mb-2">Unified Contact</h4>
                    <a href="tel:9442057033" class="text-3xl font-bold text-blue-600 hover:text-blue-800 transition-colors tracking-tight">9442057033</a>
                    <p class="text-sm text-gray-500 mt-2">Appointments, Emergencies & Reception</p>
                </div>
            </div>
        </section>
    </main>

    <!-- BOOKING VIEW -->
    <main id="view-booking" class="view-section pt-32 pb-20 min-h-screen">
        <div class="max-w-2xl mx-auto px-6 fade-in">
            <div class="flex items-center mb-8 cursor-pointer text-gray-500 hover:text-gray-900 transition-colors w-max" onclick="navigate('home')">
                <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"></path></svg>
                Back to Home
            </div>
            
            <h2 class="text-4xl font-bold tracking-tight mb-2">Schedule your visit.</h2>
            <p class="text-gray-500 mb-10">Select a date to view available time slots for dental consultation.</p>

            <form id="booking-form" class="card-glass p-8 space-y-6">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">Full Name</label>
                        <input type="text" id="b-name" required class="input-field" placeholder="John Doe">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">Phone Number</label>
                        <input type="tel" id="b-phone" required class="input-field" placeholder="9442057033">
                    </div>
                </div>

                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-2">Symptoms or Reason for Visit</label>
                    <textarea id="b-symptoms" required class="input-field min-h-[100px] resize-none" placeholder="E.g., Toothache, regular checkup, cleaning..."></textarea>
                </div>

                <div>
                    <label class="block text-sm font-medium text-gray-700 mb-2">Select Date</label>
                    <input type="date" id="b-date" required class="input-field" onchange="fetchAvailableSlots()">
                </div>

                <div id="time-slot-container" class="hidden">
                    <label class="block text-sm font-medium text-gray-700 mb-3">Available Time Slots</label>
                    <div id="slots-grid" class="grid grid-cols-3 sm:grid-cols-4 gap-3">
                        <!-- Slots injected via JS -->
                    </div>
                    <input type="hidden" id="b-time" required>
                </div>

                <div class="pt-4 border-t border-gray-100">
                    <button type="submit" id="submit-booking-btn" class="btn-primary w-full text-lg disabled:opacity-50 disabled:cursor-not-allowed">Confirm Appointment</button>
                </div>
            </form>
        </div>
    </main>

    <!-- ADMIN DASHBOARD VIEW -->
    <main id="view-admin" class="view-section pt-32 pb-20 min-h-screen bg-[#f5f5f7]">
        <div class="max-w-5xl mx-auto px-6 fade-in">
            <div class="flex justify-between items-end mb-8">
                <div>
                    <h2 class="text-3xl font-bold tracking-tight text-gray-900">Clinic Dashboard</h2>
                    <p class="text-gray-500 mt-1">Manage schedules and settings securely.</p>
                </div>
                <button onclick="logoutAdmin()" class="text-sm font-medium text-red-600 hover:text-red-800">Sign Out</button>
            </div>

            <!-- Admin Tabs -->
            <div class="flex space-x-1 bg-gray-200/50 p-1 rounded-xl w-max mb-8">
                <button onclick="switchAdminTab('appointments')" id="tab-btn-appointments" class="px-6 py-2 rounded-lg text-sm font-medium bg-white shadow-sm text-gray-900 transition-all">Appointments</button>
                <button onclick="switchAdminTab('settings')" id="tab-btn-settings" class="px-6 py-2 rounded-lg text-sm font-medium text-gray-500 hover:text-gray-900 transition-all">Settings</button>
            </div>

            <!-- Tab: Appointments -->
            <div id="tab-appointments" class="card-glass p-0 overflow-hidden border border-gray-200/60 bg-white">
                <div class="overflow-x-auto">
                    <table class="w-full text-left border-collapse">
                        <thead>
                            <tr class="bg-gray-50 border-b border-gray-100 text-xs uppercase tracking-wider text-gray-500">
                                <th class="p-4 font-medium">Date & Time</th>
                                <th class="p-4 font-medium">Patient Details</th>
                                <th class="p-4 font-medium">Symptoms/Reason</th>
                                <th class="p-4 font-medium">Status</th>
                            </tr>
                        </thead>
                        <tbody id="admin-appointments-list" class="divide-y divide-gray-100 text-sm">
                            <!-- Injected via JS -->
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- Tab: Settings -->
            <div id="tab-settings" class="hidden card-glass p-8 border border-gray-200/60 bg-white max-w-md">
                <h3 class="text-lg font-semibold mb-4">Security Settings</h3>
                <form id="change-pin-form" class="space-y-4">
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">Current PIN</label>
                        <input type="password" id="current-pin" required class="input-field" maxlength="6">
                    </div>
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-2">New PIN</label>
                        <input type="password" id="new-pin" required class="input-field" maxlength="6">
                    </div>
                    <button type="submit" class="btn-primary w-full mt-2">Update PIN</button>
                </form>
            </div>
        </div>
    </main>

    <!-- ADMIN LOGIN MODAL -->
    <div id="admin-login-modal" class="fixed inset-0 bg-gray-900/40 backdrop-blur-sm z-[60] flex items-center justify-center hidden opacity-0 transition-opacity duration-300">
        <div class="bg-white p-8 rounded-3xl shadow-2xl max-w-sm w-full mx-4 transform scale-95 transition-transform duration-300" id="login-box">
            <div class="flex justify-between items-center mb-6">
                <h3 class="text-xl font-bold tracking-tight">Admin Access</h3>
                <button onclick="closeAdminLogin()" class="text-gray-400 hover:text-gray-800">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
            </div>
            <form id="login-form">
                <input type="password" id="admin-pin-input" placeholder="Enter Secure PIN" required class="input-field text-center tracking-[0.5em] font-mono text-lg mb-6" maxlength="6">
                <button type="submit" class="btn-primary w-full">Authenticate</button>
            </form>
        </div>
    </div>

    <!-- Footer -->
    <footer class="border-t border-gray-200/60 mt-auto py-8">
        <div class="max-w-6xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center text-sm text-gray-400">
            <p>&copy; 2026 Sri Renga Dental Clinic. All rights reserved.</p>
            <div class="mt-4 md:mt-0 flex space-x-4">
                <button onclick="openAdminLogin()" class="hover:text-gray-800 transition-colors">Admin Portal</button>
            </div>
        </div>
    </footer>

    <!-- Firebase & Application Logic -->
    <script>
        // =========================================================================
        // IMPORTANT: REPLACE THIS CONFIG WITH YOUR ACTUAL FIREBASE PROJECT CONFIG
        // 1. Go to Firebase Console > Project Settings
        // 2. Add a Web App and copy the config object below.
        // 3. Ensure Firestore Database is created and rules allow read/write.
        // =========================================================================
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_PROJECT_ID.appspot.com",
            messagingSenderId: "YOUR_SENDER_ID",
            appId: "YOUR_APP_ID"
        };

        // Initialize Firebase
        if (!firebase.apps.length) {
            firebase.initializeApp(firebaseConfig);
        }
        const db = firebase.firestore();

        // -----------------------------------------------------------------
        // NAVIGATION LOGIC
        // -----------------------------------------------------------------
        function navigate(viewId) {
            document.querySelectorAll('.view-section').forEach(el => {
                el.classList.remove('active');
                el.classList.remove('fade-in');
            });
            const view = document.getElementById('view-' + viewId);
            view.classList.add('active');
            
            // Trigger reflow for animation
            void view.offsetWidth; 
            view.classList.add('fade-in');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // -----------------------------------------------------------------
        // BOOKING LOGIC & DYNAMIC TIME SLOTS
        // -----------------------------------------------------------------
        const clinicHours = [
            "09:00 AM", "09:30 AM", "10:00 AM", "10:30 AM", "11:00 AM", "11:30 AM",
            "12:00 PM", "12:30 PM", "04:30 PM", "05:00 PM", "05:30 PM", "06:00 PM", 
            "06:30 PM", "07:00 PM", "07:30 PM", "08:00 PM"
        ];

        // Restrict date picker to today onwards
        const today = new Date().toISOString().split('T')[0];
        document.getElementById('b-date').setAttribute('min', today);

        async function fetchAvailableSlots() {
            const dateStr = document.getElementById('b-date').value;
            const container = document.getElementById('time-slot-container');
            const grid = document.getElementById('slots-grid');
            
            if (!dateStr) {
                container.classList.add('hidden');
                return;
            }

            container.classList.remove('hidden');
            grid.innerHTML = '<div class="col-span-full text-center text-gray-400 text-sm py-4">Checking availability...</div>';
            document.getElementById('b-time').value = '';

            try {
                // Fetch booked slots for the selected date
                const q = db.collection("appointments").where("date", "==", dateStr);
                const querySnapshot = await q.get();
                
                const bookedTimes = [];
                querySnapshot.forEach((doc) => {
                    bookedTimes.push(doc.data().time);
                });

                // Generate UI
                grid.innerHTML = '';
                clinicHours.forEach(time => {
                    const btn = document.createElement('button');
                    btn.type = 'button';
                    btn.className = `time-slot ${bookedTimes.includes(time) ? 'disabled' : ''}`;
                    btn.innerText = time;
                    
                    if (!bookedTimes.includes(time)) {
                        btn.onclick = () => selectTime(btn, time);
                    }
                    grid.appendChild(btn);
                });
            } catch (error) {
                console.error("Error fetching slots:", error);
                grid.innerHTML = '<div class="col-span-full text-center text-red-500 text-sm py-4">Database connection error. Please contact clinic directly.</div>';
            }
        }

        function selectTime(btn, time) {
            document.querySelectorAll('.time-slot').forEach(el => el.classList.remove('selected'));
            btn.classList.add('selected');
            document.getElementById('b-time').value = time;
        }

        document.getElementById('booking-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const time = document.getElementById('b-time').value;
            if (!time) {
                alert("Please select an available time slot.");
                return;
            }

            const submitBtn = document.getElementById('submit-booking-btn');
            submitBtn.disabled = true;
            submitBtn.innerText = "Confirming...";

            const appointmentData = {
                name: document.getElementById('b-name').value,
                phone: document.getElementById('b-phone').value,
                symptoms: document.getElementById('b-symptoms').value,
                date: document.getElementById('b-date').value,
                time: time,
                timestamp: firebase.firestore.FieldValue.serverTimestamp()
            };

            try {
                await db.collection("appointments").add(appointmentData);
                alert(`Appointment confirmed for ${appointmentData.name} on ${appointmentData.date} at ${time}.`);
                document.getElementById('booking-form').reset();
                document.getElementById('time-slot-container').classList.add('hidden');
                document.getElementById('b-time').value = '';
                navigate('home');
            } catch (error) {
                console.error("Error booking appointment: ", error);
                alert("Failed to book appointment. Please check your connection or contact the clinic via phone.");
            } finally {
                submitBtn.disabled = false;
                submitBtn.innerText = "Confirm Appointment";
            }
        });

        // -----------------------------------------------------------------
        // ADMIN PORTAL LOGIC
        // -----------------------------------------------------------------
        let currentAdminPin = "1234"; // Fallback default

        // Initialize admin settings on load silently
        async function loadAdminSettings() {
            try {
                const docRef = db.collection("settings").doc("admin");
                const docSnap = await docRef.get();
                if (docSnap.exists) {
                    currentAdminPin = docSnap.data().pin || "1234";
                } else {
                    await docRef.set({ pin: "1234" });
                }
            } catch (e) {
                console.warn("Could not load settings - relying on fallback PIN.");
            }
        }
        loadAdminSettings();

        const loginModal = document.getElementById('admin-login-modal');
        const loginBox = document.getElementById('login-box');

        function openAdminLogin() {
            loginModal.classList.remove('hidden');
            setTimeout(() => {
                loginModal.classList.remove('opacity-0');
                loginBox.classList.remove('scale-95');
            }, 10);
            document.getElementById('admin-pin-input').focus();
        }

        function closeAdminLogin() {
            loginModal.classList.add('opacity-0');
            loginBox.classList.add('scale-95');
            setTimeout(() => {
                loginModal.classList.add('hidden');
                document.getElementById('login-form').reset();
            }, 300);
        }

        document.getElementById('login-form').addEventListener('submit', (e) => {
            e.preventDefault();
            const enteredPin = document.getElementById('admin-pin-input').value;
            
            if (enteredPin === currentAdminPin) {
                closeAdminLogin();
                navigate('admin');
                loadAdminAppointments();
            } else {
                alert("Incorrect PIN");
                document.getElementById('admin-pin-input').value = '';
            }
        });

        function logoutAdmin() {
            navigate('home');
        }

        function switchAdminTab(tabName) {
            document.getElementById('tab-appointments').classList.add('hidden');
            document.getElementById('tab-settings').classList.add('hidden');
            
            document.getElementById('tab-btn-appointments').classList.replace('bg-white', 'hover:text-gray-900');
            document.getElementById('tab-btn-appointments').classList.replace('shadow-sm', 'text-gray-500');
            document.getElementById('tab-btn-appointments').classList.replace('text-gray-900', 'text-gray-500');
            
            document.getElementById('tab-btn-settings').classList.replace('bg-white', 'hover:text-gray-900');
            document.getElementById('tab-btn-settings').classList.replace('shadow-sm', 'text-gray-500');
            document.getElementById('tab-btn-settings').classList.replace('text-gray-900', 'text-gray-500');

            document.getElementById('tab-' + tabName).classList.remove('hidden');
            
            const activeBtn = document.getElementById('tab-btn-' + tabName);
            activeBtn.classList.remove('text-gray-500', 'hover:text-gray-900');
            activeBtn.classList.add('bg-white', 'shadow-sm', 'text-gray-900');
        }

        async function loadAdminAppointments() {
            const listEl = document.getElementById('admin-appointments-list');
            listEl.innerHTML = '<tr><td colspan="4" class="p-8 text-center text-gray-400">Loading appointments...</td></tr>';
            
            try {
                // Fetch all appointments, ordered by date descending
                const snapshot = await db.collection("appointments").orderBy("date", "desc").get();
                listEl.innerHTML = '';
                
                if (snapshot.empty) {
                    listEl.innerHTML = '<tr><td colspan="4" class="p-8 text-center text-gray-400">No appointments found.</td></tr>';
                    return;
                }

                snapshot.forEach(doc => {
                    const data = doc.data();
                    
                    // Simple formatting for today logic
                    let dateDisplay = data.date;
                    if(data.date === today) dateDisplay = `<span class="bg-blue-100 text-blue-800 text-xs px-2 py-1 rounded-full font-medium">Today</span> ${data.date}`;

                    const row = `
                        <tr class="hover:bg-gray-50 transition-colors">
                            <td class="p-4 align-top whitespace-nowrap">
                                <div class="font-medium text-gray-900 mb-1">${dateDisplay}</div>
                                <div class="text-gray-500 flex items-center">
                                    <svg class="w-3.5 h-3.5 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                                    ${data.time}
                                </div>
                            </td>
                            <td class="p-4 align-top">
                                <div class="font-medium text-gray-900 mb-1">${data.name}</div>
                                <a href="tel:${data.phone}" class="text-blue-600 hover:underline">${data.phone}</a>
                            </td>
                            <td class="p-4 align-top max-w-xs text-gray-600 truncate whitespace-normal">${data.symptoms}</td>
                            <td class="p-4 align-top">
                                <span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-green-100 text-green-800">Confirmed</span>
                            </td>
                        </tr>
                    `;
                    listEl.innerHTML += row;
                });
            } catch (error) {
                console.error("Error loading appointments:", error);
                listEl.innerHTML = '<tr><td colspan="4" class="p-8 text-center text-red-500">Failed to load database. Check Firebase permissions.</td></tr>';
            }
        }

        // Change PIN Logic
        document.getElementById('change-pin-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const currentInput = document.getElementById('current-pin').value;
            const newPin = document.getElementById('new-pin').value;

            if (currentInput !== currentAdminPin) {
                alert("Current PIN is incorrect.");
                return;
            }
            if (newPin.length < 4) {
                alert("New PIN must be at least 4 characters.");
                return;
            }

            try {
                await db.collection("settings").doc("admin").set({ pin: newPin });
                currentAdminPin = newPin;
                alert("Security PIN updated successfully.");
                document.getElementById('change-pin-form').reset();
            } catch (error) {
                console.error("Error updating PIN:", error);
                alert("Failed to update PIN in database. Check permissions.");
            }
        });

    </script>
</body>
</html>
