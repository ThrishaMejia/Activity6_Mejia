
QUIZIVIA — PROJECT HANDOFF

Project Title: Quizivia: A Web-Based Educational Trivia Platform Academic Year: 2026 Development Status: Developed website with ongoing final testing and individual defense preparation.

Project Overview

Quizivia is a web-based educational trivia platform designed to provide users with an interactive and engaging way to practice their knowledge. It combines category-based quizzes with gamification features such as experience points, levels, daily challenges, achievements, and leaderboards. Its main purpose is to provide an alternative way of engaging with educational trivia through a game-inspired environment where users can test their knowledge, monitor their progress, and participate in different quiz activities.

Design and Brand Identity

Quizivia follows a Lavender Pixel RPG and Retro Game UI aesthetic. Its visual identity uses deep purple and lavender backgrounds, violet and soft pink accents, and gold highlights for rewards and achievements. The interface incorporates pixel-art and 16-bit-inspired decorations, rounded game-interface cards, and organized panels. The typography consists of Pixelify Sans for decorative headings, Fredoka for subheadings, and Nunito for readable body text. The platform’s mascot is a cute lavender-themed chibi student girl wearing a graduation cap and holding a quiz book, accompanied by academic elements such as trophies and question marks. All future design improvements should maintain this visual identity and remain consistent with the existing website.

Technologies Used

The project was developed using HTML for the website structure, CSS for styling and responsive layouts, and JavaScript for interactive functionality. Supabase serves as the backend platform, while PostgreSQL manages the application’s database. Supabase Edge Functions handle server-side operations such as authentication validation, retrieving questions, checking answers, and processing quiz rewards. The website is hosted through GitHub Pages.

Supabase Project URL: https://mnknxizgpkznkboingbf.supabase.co⁠￼

Private credentials, service-role keys, player tokens, and other confidential information must never be exposed in frontend code or public documentation.

Website Structure

The main website consists of several HTML pages that work together to provide the complete Quizivia experience. The index.html file serves as the Home page and contains the About section. The categories.html file displays the available quiz categories and their progress information, while category-quizzes.html allows users to choose a category and difficulty level. The quiz.html file handles category-based quiz gameplay, and daily-quiz.html provides the separate daily challenge. The quiz-results.html page displays quiz results, leaderboard.html presents player rankings, and profile.html displays player information and progress. The project also includes login.html for player authentication and admin.html for administration.

The main navigation uses icons only, representing Home, Categories, Daily Quiz, Leaderboard, Profile, and About. Visible text labels should not be added beside the icons unless specifically requested. The user previously requested that login.html and admin.html remain untouched.

Implemented Features

Quizivia includes a player authentication system that allows users to register and log in using a username and six-digit PIN. Player sessions use custom signed tokens, and player information is stored in the database.

The category-based quiz system offers History, Science, Mathematics, and General Knowledge, each with Easy, Medium, and Hard difficulty levels. Questions are retrieved dynamically from Supabase rather than being permanently hardcoded into the frontend. Each category quiz contains ten questions and has a five-minute time limit. Users select an answer and press SAVE & NEXT before proceeding to the next question. The final question uses a SUBMIT QUIZ button. Answers are checked on the server, and experience points are awarded after successful submission.

The Categories page includes category progress tracking. It displays the number of completed quizzes, total questions answered, correct answers, XP earned, accuracy percentage, and visual progress indicators. These values are retrieved through the get-category-progress Edge Function.

The Daily Quiz provides ten questions with a ten-minute time limit and allows one completed attempt per Manila calendar day. It uses stable daily questions and supports progress persistence through localStorage, allowing users to resume an unfinished quiz after refreshing the page on the same browser and device. Its reward system awards XP based on the user’s score. Users receive fifty XP for zero to two correct answers, sixty XP for three to four, seventy XP for five to six, eighty XP for seven to eight, ninety XP for nine, and one hundred XP for a perfect score. Correct answers are not revealed during gameplay or on the results page.

The platform also includes an XP and leveling system. Category-based quizzes award ten XP for every correct answer, while the Daily Quiz provides rewards ranging from fifty to one hundred XP. Every one hundred XP corresponds to one level. The Leaderboard offers Weekly and All-Time ranking views. The database supports player avatar URLs, although players without an uploaded avatar are represented using initials.

Quizivia also includes Daily Missions and Achievements. The Daily Missions feature consists of Quiz Explorer, which awards ten XP for completing a category quiz; Sharp Mind, which awards fifteen XP for achieving at least five correct answers in category quizzes; and Daily Challenger, which awards twenty XP for completing the Daily Quiz.

The Achievements feature recognizes player milestones through First Steps, Knowledge Seeker, Quiz Champion, Consistency Starter, Weekly Warrior, Knowledge Devotee, and Quizivia Legend. Their respective rewards are ten, twenty-five, one hundred, fifteen, thirty-five, seventy-five, and one hundred fifty XP. These missions and achievements use server-side qualification checks to prevent unauthorized or repeated reward claims.

Database and Backend Implementation

Quizivia uses Supabase and PostgreSQL to store and manage player information, quiz questions, quiz attempts, scores, XP, rewards, and leaderboard records. Important database tables include categories, questions, players, quiz_attempts, admin_users, quiz_sessions, daily_quiz_rewards, daily_quiz_attempts, daily_quiz_streaks, daily_mission_claims, achievement_claims, and weekly_xp. Row Level Security is enabled on important player-related tables.

The project uses several Supabase Edge Functions, including player-auth, get-player-stats, get-questions, save-quiz-result, get-daily-questions, claim-daily-reward, start-daily-quiz, get-daily-missions, claim-daily-mission, claim-achievement, get-achievement-rewards, and get-category-progress. Important database RPC functions include get_quiz_questions, check_quiz_answer, get_daily_quiz_questions, finalize_quiz_session, claim_daily_quiz_reward, start_daily_quiz_attempt, claim_daily_mission, claim_achievement, and get_quizivia_leaderboard.

Security is an important part of the implementation. Quiz answers are validated on the server instead of relying only on the user’s browser. Player sessions are validated before protected operations are performed, while XP calculations and reward qualification checks are handled through server-side functions. Daily rewards and achievements are also checked against actual player records to prevent repeated or unauthorized claims.

Current Development Status

The major website pages, icon-only navigation, category and difficulty selection, dynamic category questions, category progress tracking, Daily Quiz, weekly and all-time leaderboards, XP and leveling system, Daily Missions, Achievements, and About section have been implemented. The Supabase database and required Edge Functions have also been configured. The project has progressed to final testing and individual defense preparation.

The category quiz page, particularly quiz.html, still requires final verification. A revised version was provided to support answer selection, SAVE & NEXT interaction, a five-minute timer, progress persistence after refreshing the page, and final server-side result submission. A missing timeLeft variable was identified and corrected in the latest replacement code. The selected-answer highlight was also reported as not working, and a CSS override for .quiz-option.selected was provided. Its successful implementation still needs confirmation.

The category quiz should be tested to verify that selected answers visibly highlight, SAVE & NEXT moves to the next question, refreshing restores the current quiz progress, the final answer can still be submitted after a refresh, and XP and quiz results are saved correctly. These tests should not be considered complete until the user confirms that they work.

The Daily Quiz previously passed refresh-and-resume testing and was confirmed to hide correct-answer feedback during gameplay. Its working logic should not be modified unless a specific issue is reported. The header and navigation also need visual verification on mobile and desktop to ensure that the logo and navigation icons are centered together.

Defense Preparation and Research-Based Design Rationale

Quizivia is being prepared for an individual academic project defense. The presentation covers the project introduction, background of the study, statement of the problem, objectives, target users, proposed system, system features, gamification and reward system, system architecture, technologies, database and security, actual system demonstration, research-based design rationale, limitations, future improvements, and conclusion.

The design rationale references research by Sailer and Homner (2020), which discusses the effects of gamification on motivation, engagement, and learning; Roediger and Karpicke (2006), which discusses retrieval practice and long-term retention; Hattie and Timperley (2007), which emphasizes the importance of feedback in learning; and Dichev and Dicheva (2017), which discusses the importance of thoughtful gamification implementation in education.

These studies support the design decisions behind Quizivia, but they do not independently prove that Quizivia has improved academic performance or learning outcomes. Any claims about the platform’s actual effectiveness must be supported by the project’s own evaluation or collected data.

Limitations and Future Improvements

Although Quizivia provides several interactive features, there are still opportunities for improvement. The platform depends on its available question bank, so expanding the number of questions and educational categories would provide more variety. Future improvements may also include additional avatar customization, more personalized learning features, and expanded quiz content. These should be presented as proposed improvements rather than existing features unless they have already been implemented and tested.

Development Instructions for Future Work

The user is a nontechnical developer who works primarily through an Android phone. Communication should be in casual, friendly Taglish, with one task or instruction given at a time. Wait for the user’s confirmation before proceeding to the next task. When code needs editing, provide a complete corrected file whenever practical instead of asking the user to locate individual lines. Preserve existing working functionality and avoid changing CSS unless requested or necessary. Do not modify login.html or admin.html unless explicitly requested. Never request private credentials or secret keys. Avoid unnecessary database or SQL changes. Clearly identify which file needs editing and whether the user should replace the entire file or add a small CSS patch. Keep instructions easy to follow on a mobile device, and verify changes instead of assuming they work.

Overall Project Goal

Quizivia aims to combine educational trivia, interactive quizzes, and game-inspired progression into one web-based platform. Its goal is to make knowledge practice more accessible, organized, and engaging through category-based learning, daily challenges, and gamification.

Project Tagline: Learn, Play, Challenge.

End of Project Handoff.