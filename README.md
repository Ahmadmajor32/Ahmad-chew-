<!DOCTYPE html>
<html lang="ha">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AHMAD CHEW ACADEMY - Community Health Preparation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
</head>
<body class="bg-slate-100 text-slate-800 font-sans antialiased min-h-screen flex flex-col justify-between">

    <!-- Header / Branding -->
    <header class="bg-emerald-800 text-white shadow-md sticky top-0 z-50">
        <div class="max-w-4xl mx-auto px-4 py-3 flex justify-between items-center">
            <div onclick="showPage('home')" class="cursor-pointer">
                <h1 class="font-black text-xl tracking-wide">AHMAD CHEW ACADEMY</h1>
                <p class="text-xs text-emerald-200">By Ahmad Sani • © 2026</p>
            </div>
            <button onclick="showPage('home')" class="text-sm bg-emerald-700 hover:bg-emerald-600 px-3 py-1.5 rounded-lg border border-emerald-500">
                <i class="fa-solid fa-house mr-1"></i> Gida
            </button>
        </div>
    </header>

    <!-- MAIN CONTAINER -->
    <main class="max-w-4xl mx-auto px-4 py-6 flex-grow w-full">

        <!-- 1. HOME PAGE -->
        <section id="home-page" class="space-y-6">
            <div class="bg-gradient-to-r from-emerald-800 to-teal-900 text-white rounded-2xl p-6 text-center shadow-lg">
                <h2 class="text-2xl font-bold mb-2">Barkanku da Zuwa Ahmad CHEW Academy</h2>
                <p class="text-emerald-100 text-sm max-w-lg mx-auto">Your complete Community Health learning and examination preparation platform (CHEW & JCHEW).</p>
                
                <!-- Search Box -->
                <div class="mt-6 relative max-w-md mx-auto">
                    <input type="text" id="searchInput" onkeyup="handleSearch()" placeholder="Search courses, topics, or past questions..." 
                        class="w-full pl-10 pr-4 py-3 rounded-full text-slate-800 focus:outline-none focus:ring-2 focus:ring-amber-400 shadow">
                    <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-3.5 text-slate-400"></i>
                </div>
            </div>

            <!-- Course Library / Handouts -->
            <div>
                <h3 class="font-bold text-slate-700 text-lg mb-3">Course Library & Handouts</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div onclick="openCourse('anatomy')" class="bg-white p-5 rounded-xl shadow border border-slate-200 hover:border-emerald-600 cursor-pointer transition">
                        <span class="bg-emerald-100 text-emerald-800 text-xs font-bold px-2.5 py-1 rounded">100 Level</span>
                        <h4 class="font-bold text-lg mt-2 text-slate-800">Anatomy & Physiology</h4>
                        <p class="text-xs text-slate-500 mt-1">Cikakken Handout mai bayanin dukkan organ systems na jikin dan adam da ayyukansu.</p>
                        <div class="mt-3 flex items-center text-xs font-bold text-emerald-700">
                            <span>Bude Handout & Past Questions</span> <i class="fa-solid fa-arrow-right ml-2"></i>
                        </div>
                    </div>

                    <div onclick="openCourse('phc')" class="bg-white p-5 rounded-xl shadow border border-slate-200 hover:border-emerald-600 cursor-pointer transition">
                        <span class="bg-emerald-100 text-emerald-800 text-xs font-bold px-2.5 py-1 rounded">100 / 200 Level</span>
                        <h4 class="font-bold text-lg mt-2 text-slate-800">Primary Health Care (PHC)</h4>
                        <p class="text-xs text-slate-500 mt-1">Shikashikan PHC, Alma-Ata Declaration, MCH, Immunization, da Cold Chain.</p>
                        <div class="mt-3 flex items-center text-xs font-bold text-emerald-700">
                            <span>Bude Handout & Past Questions</span> <i class="fa-solid fa-arrow-right ml-2"></i>
                        </div>
                    </div>
                </div>
            </div>

            <!-- CBT & National Exam Practice -->
            <div>
                <h3 class="font-bold text-slate-700 text-lg mb-3">National Exam Practice (2020 - 2026)</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="bg-white p-5 rounded-xl shadow border border-slate-200 flex flex-col justify-between">
                        <div>
                            <span class="bg-emerald-100 text-emerald-800 text-xs px-2 py-1 rounded font-bold">Past Questions Mode</span>
                            <h4 class="font-bold text-lg mt-2 text-slate-800">CBT Practice By Year</h4>
                            <p class="text-xs text-slate-500 mt-1">Zaɓi shekarar jarrabawa (2020, 2021, 2022, 2023, 2024, 2025, 2026) don yin gwaji.</p>
                        </div>
                        <div class="mt-4 flex gap-2">
                            <select id="yearSelect" class="bg-slate-100 border text-xs font-bold p-2 rounded-lg text-slate-700">
                                <option value="all">Duk Shekaru (2020-2026)</option>
                                <option value="2026">2026 Past Questions</option>
                                <option value="2025">2025 Past Questions</option>
                                <option value="2024">2024 Past Questions</option>
                                <option value="2023">2023 Past Questions</option>
                                <option value="2022">2022 Past Questions</option>
                                <option value="2021">2021 Past Questions</option>
                                <option value="2020">2020 Past Questions</option>
                            </select>
                            <button onclick="startCBTWithFilter()" class="flex-grow bg-emerald-700 hover:bg-emerald-800 text-white py-2 rounded-lg font-bold text-xs">Fara CBT</button>
                        </div>
                    </div>

                    <div class="bg-white p-5 rounded-xl shadow border border-slate-200 flex flex-col justify-between">
                        <div>
                            <span class="bg-amber-100 text-amber-800 text-xs px-2 py-1 rounded font-bold">National Mock</span>
                            <h4 class="font-bold text-lg mt-2 text-slate-800">Full National Mock Exam</h4>
                            <p class="text-xs text-slate-500 mt-1">Cikakkiyar jarrabawar gwaji ta kasa mai kidayar lokaci da sakamako na gaske.</p>
                        </div>
                        <button onclick="startCBT('mock', 'all')" class="mt-4 w-full bg-amber-600 hover:bg-amber-700 text-white py-2.5 rounded-lg font-bold text-xs">Fara Full Mock Exam</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- 2. ANATOMY HANDOUT SECTION -->
        <section id="anatomy-handout-page" class="hidden space-y-4">
            <div class="flex justify-between items-center border-b pb-3">
                <button onclick="showPage('home')" class="text-emerald-700 font-bold text-sm"><i class="fa-solid fa-arrow-left"></i> Back to Courses</button>
                <span class="bg-emerald-100 text-emerald-800 text-xs font-bold px-3 py-1 rounded-full">100 Level</span>
            </div>
            
            <article class="bg-white p-6 rounded-2xl shadow space-y-6 text-slate-700">
                <div class="border-b pb-4">
                    <h2 class="text-2xl font-black text-emerald-900">Anatomy & Physiology - Complete Handout</h2>
                    <p class="text-xs text-slate-500 mt-1">AHMAD CHEW ACADEMY • Core Study Material for Community Health Students</p>
                </div>
                
                <!-- Section 1 -->
                <section class="space-y-2">
                    <h3 class="text-lg font-bold text-emerald-800">1. Introduction to Human Body Organization</h3>
                    <p class="text-sm leading-relaxed">Anatomy is the study of the structure of the human body, while Physiology is the study of how these structures function. The structural levels of organization are: <strong>Chemical → Cellular → Tissue → Organ → System → Organism</strong>.</p>
                    <div class="bg-amber-50 border-l-4 border-amber-500 p-3 text-xs text-amber-900">
                        <strong>Karin Bayani (Hausa):</strong> Anatomy yana bayani ne kan sassan jiki (kamar zuciya ko hanta), yayin da Physiology yake bayanin yadda wadannan sassa ke aiki.
                    </div>
                </section>

                <!-- Section 2 -->
                <section class="space-y-2">
                    <h3 class="text-lg font-bold text-emerald-800">2. Cardiovascular System (Tsarin Zagayen Jini)</h3>
                    <p class="text-sm leading-relaxed">Consists of the Heart, Blood Vessels (Arteries, Veins, Capillaries), and Blood. The human heart has four chambers: Left/Right Atria and Left/Right Ventricles.</p>
                    <ul class="list-disc pl-5 text-sm space-y-1">
                        <li><strong>Arteries:</strong> Carry oxygenated blood away from the heart (except Pulmonary Artery).</li>
                        <li><strong>Veins:</strong> Carry deoxygenated blood back to the heart (except Pulmonary Vein).</li>
                        <li><strong>Capillaries:</strong> Site of gas and nutrient exchange in tissues.</li>
                    </ul>
                </section>

                <!-- Section 3 -->
                <section class="space-y-2">
                    <h3 class="text-lg font-bold text-emerald-800">3. Respiratory System (Tsarin Numfashi)</h3>
                    <p class="text-sm leading-relaxed">Responsible for gas exchange (taking in Oxygen and removing Carbon Dioxide). Organs include Nose, Pharynx, Larynx, Trachea, Bronchi, and Lungs.</p>
                    <p class="text-xs bg-slate-100 p-2 rounded"><strong>Key Note:</strong> The functional unit of the lungs where gas exchange occurs is the <strong>Alveolus (plural: Alveoli)</strong>.</p>
                </section>

                <!-- Section 4 -->
                <section class="space-y-2">
                    <h3 class="text-lg font-bold text-emerald-800">4. Digestive System (Tsarin Ingestion da Narkar da Abinci)</h3>
                    <p class="text-sm leading-relaxed">Breaks down food into nutrients. Path of food: Mouth → Esophagus → Stomach → Small Intestine → Large Intestine → Anus.</p>
                    <ul class="list-disc pl-5 text-sm space-y-1">
                        <li><strong>Stomach:</strong> Secretes Hydrochloric Acid (HCl) and Pepsin to digest proteins.</li>
                        <li><strong>Small Intestine (Duodenum, Jejunum, Ileum):</strong> Main site of nutrient absorption.</li>
                        <li><strong>Large Intestine:</strong> Absorbs water and forms feces.</li>
                    </ul>
                </section>

                <!-- Section 5 -->
                <section class="space-y-2">
                    <h3 class="text-lg font-bold text-emerald-800">5. Urinary/Excretory System (Tsarin Fitai da Wanke Fiɗi)</h3>
                    <p class="text-sm leading-relaxed">Organs: Two Kidneys, Two Ureters, Urinary Bladder, and Urethra.</p>
                    <p class="text-xs bg-slate-100 p-2 rounded"><strong>Functional Unit:</strong> The functional and structural unit of the kidney is the <strong>Nephron</strong>.</p>
                </section>

                <div class="pt-4 border-t">
                    <button onclick="startCBT('practice', 'Anatomy')" class="w-full bg-emerald-700 text-white font-bold py-3 rounded-xl shadow text-sm hover:bg-emerald-800">
                        <i class="fa-solid fa-pen-to-square mr-2"></i> Practice Anatomy Past Questions (2020 - 2026)
                    </button>
                </div>
            </article>
        </section>

        <!-- 3. CBT & MOCK ENGINE -->
        <section id="cbt-page" class="hidden space-y-4">
            <div class="bg-slate-800 text-white p-4 rounded-xl flex justify-between items-center shadow">
                <div>
                    <h3 id="cbt-title" class="font-bold text-sm text-emerald-300">CBT Exam</h3>
                    <p class="text-xs text-slate-300" id="cbt-subtitle">AHMAD CHEW ACADEMY</p>
                </div>
                <div class="bg-slate-900 px-3 py-1.5 rounded-lg border border-slate-700 text-amber-400 font-mono font-bold text-sm" id="timer-display">
                    10:00
                </div>
            </div>

            <!-- Question Card -->
            <div class="bg-white p-6 rounded-2xl shadow space-y-4">
                <div class="flex justify-between text-xs font-bold text-slate-500 border-b pb-2">
                    <span id="question-number">Question 1</span>
                    <span id="question-meta" class="text-emerald-700">CHPRBN Past Question</span>
                </div>

                <p id="question-text" class="font-bold text-slate-800 text-base leading-snug">
                    Loading question...
                </p>

                <div id="options-container" class="space-y-2 pt-2">
                    <!-- Options injected by JS -->
                </div>

                <div class="flex justify-between pt-4 border-t">
                    <button onclick="prevQuestion()" id="prev-btn" class="bg-slate-200 hover:bg-slate-300 text-slate-700 font-bold px-4 py-2 rounded-lg text-sm">Baya</button>
                    <button onclick="nextQuestion()" id="next-btn" class="bg-emerald-700 hover:bg-emerald-800 text-white font-bold px-5 py-2 rounded-lg text-sm">Gaba</button>
                    <button onclick="submitCBT()" id="submit-btn" class="hidden bg-red-600 hover:bg-red-700 text-white font-bold px-5 py-2 rounded-lg text-sm">Submit Exam</button>
                </div>
            </div>
        </section>

        <!-- 4. RESULT PAGE -->
        <section id="result-page" class="hidden space-y-4 text-center">
            <div class="bg-white p-8 rounded-2xl shadow space-y-4 max-w-md mx-auto">
                <div class="w-20 h-20 bg-emerald-100 text-emerald-800 rounded-full flex items-center justify-center mx-auto text-3xl font-black" id="score-circle">
                    0%
                </div>
                <h3 class="text-2xl font-black text-slate-800">Sakamakon Jarrabawa</h3>
                <p id="result-message" class="text-sm text-slate-600">Sakamako na gaske.</p>
                
                <div class="bg-slate-50 p-4 rounded-xl border text-left text-xs space-y-2">
                    <div class="flex justify-between"><span>Total Questions:</span> <strong id="res-total">0</strong></div>
                    <div class="flex justify-between"><span>Correct Answers:</span> <strong id="res-correct" class="text-green-600">0</strong></div>
                    <div class="flex justify-between"><span>Wrong Answers:</span> <strong id="res-wrong" class="text-red-600">0</strong></div>
                </div>

                <div class="pt-2 space-y-2">
                    <button onclick="showPage('home')" class="w-full bg-emerald-700 text-white font-bold py-2.5 rounded-lg text-sm">Koma Shafin Farko</button>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-slate-800 text-slate-400 text-center py-4 text-xs border-t border-slate-700">
        <p class="font-semibold text-slate-300">AHMAD CHEW ACADEMY</p>
        <p class="mt-0.5">Designed by Ahmad Sani • © 2026 All Rights Reserved.</p>
    </footer>

    <!-- JAVASCRIPT DATABASE & ENGINE -->
    <script>
        // CIKAKKEN DATABASE NA CHPRBN PAST QUESTIONS (2020 - 2026)
        const masterQuestionBank = [
            // --- 2026 PAST QUESTIONS ---
            {
                year: 2026,
                course: "Anatomy",
                q: "What is the structural and functional unit of the human kidney?",
                options: ["Nephron", "Neuron", "Alveolus", "Hepatocyte"],
                correct: 0,
                explanation: "The nephron is responsible for filtering blood and producing urine in the kidney."
            },
            {
                year: 2026,
                course: "PHC",
                q: "The Ottawa Charter (1986) is historically associated with which major public health concept?",
                options: ["Primary Health Care", "Health Promotion", "Epidemiology", "Family Planning"],
                correct: 1,
                explanation: "The Ottawa Charter defined Health Promotion as enabling people to increase control over their health."
            },

            // --- 2025 PAST QUESTIONS ---
            {
                year: 2025,
                course: "Anatomy",
                q: "Which blood vessel carries oxygenated blood from the lungs back to the left atrium of the heart?",
                options: ["Pulmonary Artery", "Pulmonary Vein", "Aorta", "Vena Cava"],
                correct: 1,
                explanation: "Pulmonary Veins are the only veins in the human body that carry oxygenated blood."
            },
            {
                year: 2025,
                course: "PHC",
                q: "Process of transferring health information and skills to encourage healthy living is:",
                options: ["Health Education", "Counseling", "Community Entry", "Epidemiology"],
                correct: 0,
                explanation: "Health Education provides knowledge that leads to voluntary adoption of healthy practices."
            },

            // --- 2024 PAST QUESTIONS ---
            {
                year: 2024,
                course: "Anatomy",
                q: "Gas exchange between air and blood takes place in which structure of the respiratory system?",
                options: ["Bronchus", "Trachea", "Alveoli", "Larynx"],
                correct: 2,
                explanation: "Alveoli are tiny air sacs surrounded by capillaries where oxygen and CO2 exchange occurs."
            },
            {
                year: 2024,
                course: "Sociology",
                q: "A person who consistently violates established societal norms is referred to as a:",
                options: ["Deviant", "Extrovert", "Aggressive", "Introvert"],
                correct: 0,
                explanation: "In medical sociology, deviance is behavior that violates formal or informal social norms."
            },

            // --- 2023 PAST QUESTIONS ---
            {
                year: 2023,
                course: "PHC",
                q: "Which of the following is UNACCEPTABLE behavior for a professional Community Health Practitioner?",
                options: ["Showing empathy to patients", "Explaining service costs honestly", "Shouting at patients during clinic", "Maintaining patient confidentiality"],
                correct: 2,
                explanation: "Shouting or mistreating patients violates CHPRBN code of ethics."
            },
            {
                year: 2023,
                course: "Anatomy",
                q: "Which chamber of the heart pumps oxygenated blood to the entire body via the Aorta?",
                options: ["Right Atrium", "Right Ventricle", "Left Atrium", "Left Ventricle"],
                correct: 3,
                explanation: "The left ventricle has the thickest muscular wall to pump blood throughout systemic circulation."
            },

            // --- 2022 PAST QUESTIONS ---
            {
                year: 2022,
                course: "PHC",
                q: "What is the primary function of the Cold Chain system in Community Health?",
                options: ["Storing surgical tools", "Preserving vaccine potency at recommended temperatures", "Cooling patient wards", "Storing cadavers"],
                correct: 1,
                explanation: "Cold Chain ensures vaccines are kept within 2°C to 8°C from manufacture to administration."
            },

            // --- 2021 PAST QUESTIONS ---
            {
                year: 2021,
                course: "Nutrition",
                q: "In screening children aged 6-59 months for malnutrition, MUAC stands for:",
                options: ["Mid-Upper Arm Circumference", "Main Under-Age Care", "Medical Upper Arm Control", "Minimum Unified Arm Measure"],
                correct: 0,
                explanation: "MUAC tape is a rapid community tool used by CHEWs to detect acute malnutrition."
            },

            // --- 2020 PAST QUESTIONS ---
            {
                year: 2020,
                course: "PHC",
                q: "Which international conference introduced Primary Health Care (PHC) in 1978?",
                options: ["Alma-Ata Declaration", "Geneva Convention", "Abuja Accord", "Tokyo Conference"],
                correct: 0,
                explanation: "The Alma-Ata conference in Kazakhstan declared PHC as the primary strategy for Health for All."
            }
        ];

        let activeQuestions = [];
        let currentIndex = 0;
        let userAnswers = {};
        let timerInterval = null;

        function showPage(pageId) {
            document.querySelectorAll('main > section').forEach(sec => sec.classList.add('hidden'));
            document.getElementById(pageId + '-page').classList.remove('hidden');
            window.scrollTo(0, 0);
        }

        function openCourse(courseKey) {
            if (courseKey === 'anatomy') {
                showPage('anatomy-handout');
            } else {
                alert('Primary Health Care Handout section is loading...');
            }
        }

        function startCBTWithFilter() {
            const selectedYear = document.getElementById('yearSelect').value;
            startCBT('practice', 'all', selectedYear);
        }

        function startCBT(mode, courseFilter = 'all', yearFilter = 'all') {
            activeQuestions = masterQuestionBank.filter(q => {
                let matchesCourse = (courseFilter === 'all') || (q.course.toLowerCase() === courseFilter.toLowerCase());
                let matchesYear = (yearFilter === 'all') || (q.year.toString() === yearFilter.toString());
                return matchesCourse && matchesYear;
            });

            if (activeQuestions.length === 0) {
                alert("Babu tambayoyi a karkashin wannan shekarar tukuna. Zabi wata shekarar!");
                return;
            }

            currentIndex = 0;
            userAnswers = {};
            
            document.getElementById('cbt-title').innerText = mode === 'mock' ? 'NATIONAL MOCK EXAMINATION' : `CBT PRACTICE (${yearFilter === 'all' ? '2020-2026' : yearFilter})`;
            document.getElementById('cbt-subtitle').innerText = `Total Questions: ${activeQuestions.length}`;
            
            showPage('cbt');
            loadQuestion();
            startTimer(mode === 'mock' ? 600 : 300);
        }

        function loadQuestion() {
            const q = activeQuestions[currentIndex];
            document.getElementById('question-number').innerText = `Question ${currentIndex + 1} of ${activeQuestions.length}`;
            document.getElementById('question-meta').innerText = `${q.year} National Exam (${q.course})`;
            document.getElementById('question-text').innerText = q.q;

            const optsContainer = document.getElementById('options-container');
            optsContainer.innerHTML = '';

            q.options.forEach((opt, idx) => {
                const isSelected = userAnswers[currentIndex] === idx;
                const btn = document.createElement('button');
                btn.className = `w-full text-left p-3.5 rounded-xl border text-sm font-medium transition ${isSelected ? 'bg-emerald-100 border-emerald-600 text-emerald-900 font-bold' : 'bg-slate-50 border-slate-200 hover:bg-slate-100'}`;
                btn.innerHTML = `<span class="inline-block w-6 text-slate-500 font-bold">${String.fromCharCode(65 + idx)}.</span> ${opt}`;
                btn.onclick = () => {
                    userAnswers[currentIndex] = idx;
                    loadQuestion();
                };
                optsContainer.appendChild(btn);
            });

            document.getElementById('prev-btn').style.visibility = currentIndex === 0 ? 'hidden' : 'visible';
            if (currentIndex === activeQuestions.length - 1) {
                document.getElementById('next-btn').classList.add('hidden');
                document.getElementById('submit-btn').classList.remove('hidden');
            } else {
                document.getElementById('next-btn').classList.remove('hidden');
                document.getElementById('submit-btn').classList.add('hidden');
            }
        }

        function nextQuestion() {
            if (currentIndex < activeQuestions.length - 1) {
                currentIndex++;
                loadQuestion();
            }
        }

        function prevQuestion() {
            if (currentIndex > 0) {
                currentIndex--;
                loadQuestion();
            }
        }

        function startTimer(seconds) {
            clearInterval(timerInterval);
            let timeLeft = seconds;
            const timerEl = document.getElementById('timer-display');

            timerInterval = setInterval(() => {
                let mins = Math.floor(timeLeft / 60);
                let secs = timeLeft % 60;
                timerEl.innerText = `${mins < 10 ? '0' : ''}${mins}:${secs < 10 ? '0' : ''}${secs}`;

                if (timeLeft <= 0) {
                    clearInterval(timerInterval);
                    alert("Lokacin jarrabawa ya kare!");
                    submitCBT();
                }
                timeLeft--;
            }, 1000);
        }

        function submitCBT() {
            clearInterval(timerInterval);
            let correctCount = 0;

            activeQuestions.forEach((q, idx) => {
                if (userAnswers[idx] === q.correct) {
                    correctCount++;
                }
            });

            const total = activeQuestions.length;
            const percentage = Math.round((correctCount / total) * 100);

            document.getElementById('score-circle').innerText = `${percentage}%`;
            document.getElementById('res-total').innerText = total;
            document.getElementById('res-correct').innerText = correctCount;
            document.getElementById('res-wrong').innerText = total - correctCount;

            const msgEl = document.getElementById('result-message');
            if (percentage >= 75) {
                msgEl.innerText = "Madalla! Sakamako mai kyau sosai. Ka shirya domin National Exam!";
                msgEl.className = "text-sm text-green-600 font-bold";
            } else {
                msgEl.innerText = "Kayi kokari, amma ana bukatar maimaita karatun Handouts domin samun maki mai girma.";
                msgEl.className = "text-sm text-amber-600 font-bold";
            }

            showPage('result');
        }

        function handleSearch() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            if (query.includes('anatomy') || query.includes('body')) {
                openCourse('anatomy');
            }
        }
    </script>
</body>
</html>
