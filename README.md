<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HoopsHype Revamped - Cyro Asseo's Big Board</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/feather-icons"></script>
    <style>
        :root {
            --hoops-red: #c8102e;
            --hoops-dark: #012637;
            --hoops-gray: #f5f5f5;
            --hoops-border: #e0e0e0;
            --hoops-text: #333;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Roboto', 'Helvetica Neue', Arial, sans-serif;
        }
        
        body {
            background-color: var(--hoops-gray);
            color: var(--hoops-text);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-top {
            background-color: var(--hoops-dark);
            padding: 8px 0;
        }
        
        .header-main {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo img {
            height: 40px;
            margin-right: 10px;
        }
        
        .logo h1 {
            font-size: 28px;
            font-weight: 700;
            color: var(--hoops-red);
        }
        
        .logo span {
            font-weight: 400;
            color: var(--hoops-text);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav li {
            margin-left: 25px;
        }
        
        nav a {
            text-decoration: none;
            color: white;
            font-weight: 500;
            transition: color 0.3s;
            font-size: 16px;
        }
        
        nav a:hover {
            color: var(--hoops-red);
        }
        
        nav a.active {
            color: var(--hoops-red);
        }
        
        .search-bar {
            display: flex;
            align-items: center;
            background-color: var(--hoops-gray);
            border-radius: 4px;
            padding: 6px 12px;
            width: 300px;
        }
        
        .search-bar input {
            border: none;
            background: transparent;
            outline: none;
            width: 100%;
            font-size: 14px;
        }
        
        .search-bar i {
            color: #777;
            margin-right: 8px;
        }
        
        .prospect-row {
            cursor: pointer;
            transition: background-color 0.2s;
        }
        
        .prospect-row:hover {
            background-color: rgba(200, 16, 46, 0.05);
        }
        
        .profile-link {
            color: var(--hoops-red);
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            padding: 6px 12px;
            border: 1px solid var(--hoops-red);
            border-radius: 4px;
            display: inline-block;
            transition: all 0.3s;
        }
        
        .profile-link:hover {
            background-color: var(--hoops-red);
            color: white;
        }
        
        /* Modal Styles */
        #player-modal {
            display: none;
            position: fixed;
            inset: 0;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            padding: 16px;
            align-items: center;
            justify-content: center;
        }
        
        #player-modal.modal-open {
            display: flex;
        }
        
        #player-modal > div {
            margin: auto;
        }
        
        @media (max-width: 768px) {
            .header-main {
                flex-direction: column;
                align-items: flex-start;
            }
            
            nav ul {
                margin-top: 15px;
            }
            
            .search-bar {
                margin-top: 15px;
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-top">
            <div class="container">
                <nav>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">NBA News</a></li>
                        <li><a href="#">Rumors</a></li>
                        <li><a href="#">Trade Tracker</a></li>
                        <li><a href="#">Rumors Database</a></li>
                        <li><a href="#" class="active">NBA Draft</a></li>
                    </ul>
                </nav>
            </div>
        </div>
        <div class="container">
            <div class="header-main">
                <div class="logo">
                    <h1>Hoops<span>Hype</span></h1>
                </div>
                <div class="search-bar">
                    <i class="fas fa-search"></i>
                    <input type="text" placeholder="Search prospects...">
                </div>
            </div>
        </div>
    </header>
    
    <main class="container mx-auto px-4 py-8">
        <div class="max-w-6xl mx-auto">
            <div class="bg-white rounded-xl shadow-xl overflow-hidden mb-8">
                <div class="bg-gradient-to-r from-red-600 to-red-800 p-6">
                    <h1 class="text-3xl md:text-4xl font-bold text-white tracking-wide">
                        CYRO ASSEO'S BIG BOARD
                    </h1>
                    <h2 class="text-xl md:text-2xl text-yellow-300 font-semibold mt-2">
                        TOP 100 PROSPECTS - 2025 NBA DRAFT
                    </h2>
                </div>
                <div class="p-6 md:p-8">
                    <div class="flex flex-col md:flex-row justify-between items-center mb-6 space-y-4 md:space-y-0">
                        <div class="relative w-full md:w-auto">
                            <input type="text" id="search-input" placeholder="Search prospects..." 
                                   class="w-full md:w-80 pl-10 pr-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-red-500">
                            <i data-feather="search" class="absolute left-3 top-3.5 text-gray-400" style="width: 20px; height: 20px;"></i>
                        </div>
                        <div class="flex space-x-2">
                            <button class="px-4 py-2 bg-gray-200 rounded-lg hover:bg-gray-300 transition">
                                <i data-feather="download" class="inline mr-2" style="width: 16px; height: 16px;"></i> Export
                            </button>
                        </div>
                    </div>
                    
                    <div class="overflow-x-auto shadow rounded-lg">
                        <table class="w-full">
                            <thead>
                                <tr class="bg-gray-100 text-left text-gray-700 font-bold">
                                    <th class="px-6 py-4">Rank</th>
                                    <th class="px-6 py-4">Player</th>
                                    <th class="px-6 py-4 hidden sm:table-cell">Position</th>
                                    <th class="px-6 py-4 hidden lg:table-cell">School/Team</th>
                                    <th class="px-6 py-4 text-center">Profile</th>
                                </tr>
                            </thead>
                            <tbody id="prospects-list" class="divide-y divide-gray-200">
                                <!-- Prospects will be inserted here by JavaScript -->
                            </tbody>
                        </table>
                    </div>
                    <div class="mt-8 flex justify-between items-center">
                        <div class="text-gray-600">
                            Showing <span class="font-bold">100</span> of 100 prospects
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

        <div class="disclaimer">
            <p><strong>Note:</strong> For any data errors or updates, please contact: <a href="mailto:hoopshype@hoopshype.com">hoopshype@hoopshype.com</a> or <a href="mailto:casseo@gannett.com">casseo@gannett.com</a></p>
        </div>
    </main>
    

    
    <script>
    
    <!-- Player Modal -->
    <div id="player-modal">
        <div class="bg-white rounded-xl max-w-4xl w-full max-h-[90vh] overflow-y-auto">
            <div class="sticky top-0 bg-white px-6 py-4 border-b flex justify-between items-center">
                <h3 id="modal-title" class="text-2xl font-bold"></h3>
                <button id="close-modal" class="text-gray-500 hover:text-gray-700">
                    <i data-feather="x" style="width: 24px; height: 24px;"></i>
                </button>
            </div>
            <div id="modal-content" class="p-6">
                <!-- Content will be loaded here -->
            </div>
        </div>
    </div>
            






    <script src="https://cdn.jsdelivr.net/npm/vanta@latest/dist/vanta.globe.min.js"></script>
    <script>
        // Prospect Data
        const prospects = [
            { rank: 1, name: "Darryn Peterson", position: "SG", school: "Kansas", height: "6-6", weight: "195 lbs", wingspan: "6-10", class: "Freshman", bestRank: 1, worstRank: 2, summary: "A prototypical sized jumbo guard who can play one through three and has the mature vibe of a 30-year-old. He is arguably the most complete scoring guard prospect of the past decade, with an advanced feel for creation, pacing, and shot-making. He's a natural scorer who can hit tough pull-ups and operate as a lead guard or off-ball cutter. He possesses advantageous athletic traits and good lateral quickness for defense, projecting as an immediate plus. He has the body to guard bigger wings and the athleticism for quicker guards and could defend every position except centers once he bulks up. Some scouts believe he may be better than 2025's No. 1 pick, Cooper Flagg.", nbaComp: "stoic James Harden" },
            { rank: 2, name: "Cameron Boozer", position: "PF/C", school: "Duke", height: "6-9", weight: "245 lbs", wingspan: "7-1", class: "Freshman", bestRank: 1, worstRank: 3, summary: "The son of Carlos Boozer and twin brother of Cayden Boozer, he's a truly special prospect with a pro-ready frame built on high-IQ decision-making, efficiency, and fundamental skill. He plays like a beast with elite rebounding skills, soft hands, and great footwork, and he throws outlet passes reminiscent of Kevin Love. He can jump high for putbacks and has a nice touch up to 17 feet, opening up his pick-and-pop game. He's a polished, productive, and unselfish natural four who can be a switch big and make an instant frontcourt impact.", nbaComp: "Al Horford, Kevin Love" },
            { rank: 3, name: "AJ Dybantsa", position: "PF/SF", school: "BYU", height: "6-9", weight: "210 lbs", wingspan: "7-0", class: "Freshman", bestRank: 1, worstRank: 3, summary: "A consensus top prospect with special athletic abilities and advanced shot-making. He combines explosiveness with strong body control to generate offense at the rim. He has crazy defensive skills, hops like you wouldn't believe, and is a block-hunter who loves to create turnovers, capable of playing both the three and four positions. His takeover scoring comes from ball-handling, a rise-and-fire jumper, and advanced footwork, projecting as an All-NBA caliber two-way franchise cornerstone. He needs to work on his half-court game and improve his defensive consistency and decision-making.", nbaComp: "Aaron Gordon/Jonathan Isaac" },
            { rank: 4, name: "Nate Ament", position: "SF/PF", school: "Tennessee", height: "6-10", weight: "185 lbs", wingspan: "7-0", class: "Freshman", bestRank: 4, worstRank: 7, summary: "A fast-rising 'wild card' with elite size, length, and the skill set of a forward who can shoot. He possesses a smooth jumper, tightening ball-handling, and shooting versatility, reminiscent of Kevin Durant or Brandon Ingram. He has the lowest floor out of the Top 4 but arguably the second-highest ceiling (behind Peterson) if it all clicks. The catch is he tends to fade when the game gets physical and can become passive. He needs to bulk up and stay consistent to fulfill his star upside.", nbaComp: "Harrison Barnes/ Zaccharie Risacher" },
            { rank: 5, name: "Mikel Brown", position: "PG", school: "Louisville", height: "6-5", weight: "173 lbs", wingspan: "6-6", class: "Freshman", bestRank: 5, worstRank: 14, summary: "A super quick, shifty, and dynamic player who can create space to score and is considered the top pure point guard in the draft despite a score-first mentality. His stock is soaring after strong international play (47.6% from three, 43 assists to 15 turnovers at the U19 World Cup). He manipulates defenses in pick-and-roll situations and has explosive athletic ability with deep, confident range. He's more of a scoring guard like Coby White than a floor general. He needs to sharpen his decision-making and add muscle to be a strong starter or great spark off the bench.", nbaComp: "Coby White" },
            { rank: 6, name: "Jayden Quaintance", position: "PF/C", school: "Kentucky", height: "6-10", weight: "250 lbs", wingspan: "7-5", class: "Sophomore", bestRank: 4, worstRank: 13, summary: "A springy, explosive, and athletic big forward with an NBA-level frame and huge reach. He plays like a center still working on becoming a forward, and might be the most versatile big in this class. He's an explosive target for lobs and showed outstanding shot-blocking instincts (9.8 block percentage), capable of hanging with guards on the perimeter. His offense is limited to easy dunks and put-backs, and he needs to improve his shooting range and half-court creation. The key question is whether he is a four or an undersized five.", nbaComp: "N/A" },
            { rank: 7, name: "Karim Lopez", position: "SF/PF", school: "New Zealand Breakers", height: "6-8", weight: "210 lbs", wingspan: "6-11", class: "2007", bestRank: 5, worstRank: 18, summary: "Heralded as the future face of Mexican basketball (playing for the NZ Breakers NBL Next Stars), he's a highly skilled forward with a decent handle, okay jumper, and good size. He's at his best attacking closeouts. He doesn't have one elite skill that stands out, leading some to label him as a 'Georges Niang with extra length.' His draft stock is closely tied to continued shooting development (21 made threes in 25 games) and strengthening his dribble, as his mechanics can be rigid and he lacks a pull-up.", nbaComp: "latino Deni Avdija" },
            { rank: 8, name: "Chris Cenac Jr.", position: "C", school: "Houston", height: "6-11", weight: "233 lbs", wingspan: "7-4", class: "Freshman", bestRank: 5, worstRank: 16, summary: "Projects as an anchor for Houston due to his stunning 7-4' wingspan and good open-court athleticism. He has impressive footwork for a big guy, soft touch around the basket, and is capable of hitting threes and difficult isolation jumpers, showing unique shot-making for his size. He can switch easily between defensive schemes and has great timing as a shot-blocker. He still has some raw facets to his game in footwork and ball-handling but could turn into a rim-runner and shot-blocking specialist with more playtime.", nbaComp: "N/A" },
            { rank: 9, name: "Caleb Wilson", position: "PF/C", school: "North Carolina", height: "6-9", weight: "205 lbs", wingspan: "7-0", class: "Freshman", bestRank: 6, worstRank: "NR", summary: "A long, springy forward oozing with upside, valued for his fluid movement, flashes of impressive skills, and instincts on defense. His mid-range game is lethal, and he's a tremendous defender capable of defending in space. His motor is not always revving, but when unleashed, he's a freak of nature. However, he needs to put his game together consistently and improve his outside shooting and self-creation. Clear potential to become a modern two-way forward if he can amp up his motor.", nbaComp: "Jarace Walker" },
            { rank: 10, name: "Tounde Yessoufou", position: "SG/SF", school: "Baylor", height: "6-5", weight: "215 lbs", wingspan: "6-9", class: "Freshman", bestRank: 4, worstRank: "NR", summary: "A powerhouse athlete who looks like a grown man with a chiseled frame, he's a force who imposes his will on both ends, capable of guarding multiple positions and attacking the rim aggressively. He will remind people of Anthony Edwards at first glance, though he is not in the same stratosphere. He's transitioning to a more skilled player, showing improved footwork, touch, and shooting. If he develops a reliable catch-and-shoot game, he might become a fantastic 3-and-D starter or an explosive energy guy off the bench.", nbaComp: "Isaac Okoro/Josh Okogie" },
            { rank: 11, name: "Dash Daniels", position: "SG/SF", school: "Melbourne United, Australia", height: "6-6", weight: "190 lbs", wingspan: "6-10", class: "2007", bestRank: 9, worstRank: "NR", summary: "Dyson Daniels’ younger brother is a talented wing who can score from everywhere with ease and has the same killer defensive instincts his brother is known for. His smooth release makes him deadly against closeouts, and he has a knack for creating plays. He is more of a swingman who can guard one through four when he bulks up. He has average recovery speed but could fit well as a late-lottery player who can step in and shoot, with the potential to become a versatile two-way starter.", nbaComp: "Dyson Daniels/Alex Caruso" },
            { rank: 12, name: "Koa Peat", position: "PF/C", school: "Arizona", height: "6-8", weight: "235 lbs", wingspan: "6-11", class: "Freshman", bestRank: 4, worstRank: 18, summary: "A frontcourt player whose brother is NFL lineman Andrus Peat, he's a physically strong, do-it-all forward with a complete game and a bully-ball mentality inside. With quick footwork, he takes advantage of post mismatches and can stretch the floor. He combines strength/physicality with improving touch and mid-range shot-making (pull-ups and fallaways). He could be a gritty, undersized switch big, similar to Isaiah Stewart and could really shine as a small-ball five if he improves his lateral quickness and rim protection timing.", nbaComp: "Isaiah Stewart" },
            { rank: 13, name: "Isaiah Evans", position: "SG/SF", school: "Duke", height: "6-7", weight: "170 lbs", wingspan: "6-10", class: "Sophomore", bestRank: 11, worstRank: "NR", summary: "A long, wiry volume three-point shooter with a quick release who can shoot from way beyond the NBA three-point line. He withdrew from the 2025 NBA Draft to return to Duke. He has a high ceiling but is raw and needs to bulk up. If he can add muscle, ball-handling, and improve his shot creation, he could develop into a go-to scorer and a solid two-way player in the rotation.", nbaComp: "N/A" },
            { rank: 14, name: "Bennett Stirtz", position: "PG", school: "Iowa", height: "6-4", weight: "180 lbs", wingspan: "6-7", class: "Senior", bestRank: 9, worstRank: 35, summary: "A crafty offensive talent known for his great shooting off the move and crafty handles. He's a combo guard who followed coach Ben McCollum to Iowa, expected to be an obedient soldier in McCollum's scheme. He is emerging as a high-level prospect with a game built on creativity, shotmaking, and high IQ. If he can prove to be efficient against tough Big Ten competition, he'll solidify his value as a go-to shooter and secondary playmaker.", nbaComp: "N/A" },
            { rank: 15, name: "Yaxel Lendeborg", position: "PF", school: "Michigan", height: "6-9", weight: "235 lbs", wingspan: "7-4", class: "Senior", bestRank: 11, worstRank: 28, summary: "A well-built, fundamentally sound big forward who withdrew from the 2025 NBA Draft after being a potential first-round pick. He does a bit of everything: initiates fast breaks, makes plays on the move, scores from all over the court, snags rebounds, and switches on defense. He put up elite two-way counting stats, suggesting a 'Swiss Army Knife' role. If he can tighten up his jumper and make cleaner decisions, he might fit the mold of a versatile two-way frontcourt player at the next level.", nbaComp: "Guerschon Yabusele" },
            { rank: 16, name: "Dame Sarr", position: "SG/SF", school: "Duke", height: "6-7", weight: "195 lbs", wingspan: "6-11", class: "2006", bestRank: 9, worstRank: "NR", summary: "The highly anticipated Italian wing arrives from Barcelona with an intriguing blend of defensive versatility and shooting ability. He is expected to showcase his dynamic slashing capabilities in transition and the half-court. His athleticism and defensive length are highly enticing. Scouts want to see improvements in his off-ball shooting and decision-making when driving. Should his court awareness match his physical tools, he has the potential to emerge as a Top 10 two-way wing in the league.", nbaComp: "Jaylen Clarke, Bilal Coulibaly" },
            { rank: 17, name: "Tahaad Pettiford", position: "PG", school: "Auburn", height: "6-1", weight: "172 lbs", wingspan: "6-5", class: "Sophomore", bestRank: 14, worstRank: "NR", summary: "Auburn's lead guard is a dynamic scorer with a knack for quick bursts of speed, adept at hitting pull-up three-pointers and fearlessly attacking the rim. He showed enough at the 2025 NBA Draft Combine to receive feedback. His shorter stature may limit his margin for error, making it essential for him to improve his playmaking abilities and on-ball defense to solidify late-first-round buzz.", nbaComp: "N/A" },
            { rank: 18, name: "Labaron Philon", position: "PG/SG", school: "Alabama", height: "6-4", weight: "175 lbs", wingspan: "6-6", class: "Sophomore", bestRank: 10, worstRank: "NR", summary: "A creative playmaker with an advanced understanding of the game. He navigates the court brilliantly, using changes in pace and clever off-ball movements to manipulate defenses. He has a herky-jerky style of play that will suit the NBA if he can improve his shot. Adding 10 pounds of muscle and developing a more consistent catch-and-shoot game could elevate his high basketball IQ into tangible first-round value.", nbaComp: "Monta Ellis, Keyon Dooling" },
            { rank: 19, name: "Karter Knox", position: "SF/PF", school: "Arkansas", height: "6-6", weight: "215 lbs", wingspan: "6-10", class: "Sophomore", bestRank: 16, worstRank: "NR", summary: "The younger brother of Kevin Knox has shown significant growth, finishing last season with a solid season shooting from deep. He combines straight-line explosiveness with an improved shooting stroke. If he can maintain his jumper while tightening his ball-handling skills, he could transform into a valuable plug-and-play scoring wing.", nbaComp: "Dion Waiters, Brice Sensabaugh" },
            { rank: 20, name: "Boogie Fland", position: "PG", school: "Florida", height: "6-3", weight: "172 lbs", wingspan: "6-6", class: "Sophomore", bestRank: 8, worstRank: "NR", summary: "A maestro of the pick-and-roll with one of the best-looking shots in college basketball, who can shift speeds and drain long-range shots. He's an ultra-quick lead guard who must find a balance between his scoring instinct and playmaking responsibilities. He needs to be more consistent from deep as an undersized guard. Florida's fast-paced style will allow him to showcase his ability as a capable facilitator, not just a scorer.", nbaComp: "Rob Dillingham, Darius Garland" },
            { rank: 21, name: "Braylon Mullins", position: "SG/SF", school: "UConn", height: "6-5", weight: "185 lbs", wingspan: "6-7", class: "Freshman", bestRank: 7, worstRank: "NR", summary: "One of the most lethal movement shooters in this class, boasting a staggering three-point shot during AAU. He joins Dan Hurley’s screen-heavy offense, which will showcase his movement shooting and footwork off screens. His tenacious defense at the point-of-attack will keep him on the floor. His ability to make quick decisions and create off-ball movement hints at substantial one-and-done potential if he can be consistent.", nbaComp: "N/A" },
            { rank: 22, name: "Nikolas Khamenia", position: "PF/SF", school: "Duke", height: "6-8", weight: "215 lbs", wingspan: "6-9", class: "Freshman", bestRank: 5, worstRank: "NR", summary: "An exciting talent who plays like a point guard while having a forward's body. He processes the game super fast, can make fancy passes with either hand, and has reliable shooting range (44.0% from three at U19 World Cup). He needs to solidify his position as a combo forward and avoid being labeled a 'tweener.' If he improves his burst and adds strength, he’ll be a smart playmaker in any lineup.", nbaComp: "N/A" },
            { rank: 23, name: "Thomas Haugh", position: "SF/PF/C", school: "Florida", height: "6-9", weight: "210 lbs", wingspan: "6-11", class: "Junior", bestRank: 15, worstRank: "NR", summary: "The Gators’ 'hidden gem,' he's a versatile combo-forward who fits the modern-day four position as a utility player that can moonlight as a stretch five. He combines the agility to switch on defense, explosive leaping ability, and an emerging shooting touch from beyond the arc (34% on attempts). An increase in his role, given the team's significant jump in net rating during his minutes, could catapult him into first-round consideration.", nbaComp: "Santi Aldama/Dean Wade" },
            { rank: 24, name: "Darius Acuff Jr.", position: "PG", school: "Arkansas", height: "6-3", weight: "180 lbs", wingspan: "6-6", class: "Freshman", bestRank: 5, worstRank: "NR", summary: "An explosive lead guard with a strong, thicker build and lower center of gravity, paired with downhill speed and impressive shooting range. He's wired to score and is nearly impossible to keep out of the lane. He can be a dynamic facilitator in the pick-and-roll. His success hinges on his consistency as a decision-maker and his commitment to defensive responsibilities.", nbaComp: "N/A" },
            { rank: 25, name: "Alijah Arenas", position: "SG/SF", school: "USC", height: "6-7", weight: "197 lbs", wingspan: "7-0", class: "Freshman", bestRank: 9, worstRank: "NR", summary: "The son of Gilbert Arenas, he is a massive combo guard who can play the wing. He displays an impressive skill set with the footwork and confidence of a professional scorer, with the ability to score on all three levels and guard one through three. He is currently recovering from a serious car crash. If he can regain his quickness and shot-creating ability, the 18-year-old still holds the potential to be a high lottery selection.", nbaComp: "N/A" },
            { rank: 26, name: "Alex Condon", position: "C", school: "Florida", height: "7-0", weight: "222 lbs", wingspan: "7-0", class: "Junior", bestRank: 19, worstRank: "NR", summary: "A mobile seven-footer with soft hands and exceptional grab-and-go capabilities. He possesses a budding proficiency in pick-and-pop situations and plays with a stereotypical Aussie grit, doing the dirty work. He's an athletic finisher and defensive presence but must become more assertive in securing rebounds and consistently protecting the rim to elevate his status.", nbaComp: "N/A" },
            { rank: 27, name: "JT Toppin", position: "PF", school: "Texas Tech", height: "6-9", weight: "210 lbs", wingspan: "7-1", class: "Junior", bestRank: 23, worstRank: "NR", summary: "A workhorse known for his relentless motor, he excels at rebounding (arguably the best non-big rebounder in the nation), smooth transitioning, switching onto wing players, and displaying flashes of face-up scoring. He's a force around the basket with great touch and instincts. By honing his corner three-point shooting and enhancing his short-roll passing, he can scale his energizing style into NBA rotations.", nbaComp: "Taj Gibson, Carl Landry" },
            { rank: 28, name: "Miles Byrd", position: "SG/SF", school: "San Diego State", height: "6-6", weight: "182 lbs", wingspan: "6-10", class: "Junior", bestRank: 17, worstRank: "NR", summary: "A defensive playmaker with impressive stats, including 2.1 steals and 1.1 blocks per game (4.3 steal percentage). He has keen passing vision (18.2 assist percentage) and a solid free-throw percentage, which foreshadows his shooting potential. He has the makings of a Swiss army knife-type of wing. His career shooting from three remains the lone barrier between him and true 3-and-D status.", nbaComp: "N/A" },
            { rank: 29, name: "Ian Jackson", position: "SG/SF", school: "St. John’s", height: "6-5", weight: "190 lbs", wingspan: "6-8", class: "Sophomore", bestRank: 15, worstRank: "NR", summary: "An explosive athlete who is a blur in the open court and an elite above-the-rim player. He showcases the ability to score from all three levels but needs improvement in decision-making (tunnel vision as a passer) and defensive discipline (effort wanes at times). He still lacks efficiency but a breakout season under Rick Pitino’s guidance could reignite his trajectory toward a Top 15 selection.", nbaComp: "N/A" },
            { rank: 30, name: "Joseph Tugler", position: "PF", school: "Houston", height: "6-7", weight: "230 lbs", wingspan: "7-6", class: "Junior", bestRank: 21, worstRank: "NR", summary: "Widely regarded as one of college basketball's best defenders. He is a strong, long-armed power forward who excels at erasing mistakes with remarkable ground coverage and impressive vertical leaping ability (wingspan almost a foot longer than height). He will be a day one plus-help defender and weakside rim protector in the NBA. Offensively, his game is limited to cuts and rolls, but even developing a reliable corner three-point shot would enhance his NBA readiness.", nbaComp: "Kenneth Faried" },
            { rank: 31, name: "Cayden Boozer", position: "PG", school: "Duke", height: "6-4", weight: "190 lbs", wingspan: "6-5", class: "Freshman", bestRank: 11, worstRank: "NR", summary: "A highly talented 5-star point guard with great size, feel for the game, and high playmaking IQ. He prioritizes setting up teammates first, consistently logging high assist numbers with willing vision off penetration. While not an explosive scorer, he has made strides with his shotmaking and range, and has excellent touch on his floater. Inconsistent shooting is his main area of concern.", nbaComp: "N/A" },
            { rank: 32, name: "Kam Williams", position: "SF", school: "Kentucky", height: "6-8", weight: "200 lbs", wingspan: "7-0", class: "Sophomore", bestRank: 17, worstRank: "NR", summary: "A long, smooth wing with prototypical NBA athleticism, excellent positional size, and a 7-foot wingspan. He's a highly efficient scorer, converting 41.2% from three on significant volume for a freshman, making him one of the more projectable shooters among returning prospects. He projects as a positive defender (1.4 steals, 1.1 blocks per game) with a high floor as a 3-and-D contributor. To maximize his draft stock, he needs to increase his offensive volume, develop a more reliable pull-up jumper, and improve his screen navigation as an on-ball defender.", nbaComp: "Cam Johnson / Trey Murphy III" },
            { rank: 33, name: "Meleek Thomas", position: "SG", school: "Arkansas", height: "6-4", weight: "185 lbs", wingspan: "6-6", class: "Freshman", bestRank: 9, worstRank: "NR", summary: "A silky smooth scoring guard with a high skill level and feel for the game. He is a dangerous one-on-one player capable of scoring off a variety of moves (step-backs, turnarounds, floaters). He should draw attention with his self-creation and shotmaking, but will have to compete for touches in the Arkansas backcourt, potentially limiting his development as a lead guard/playmaker.", nbaComp: "N/A" },
            { rank: 34, name: "Isiah Harwell", position: "SG/SF", school: "Houston", height: "6-5", weight: "200 lbs", wingspan: "6-9", class: "Freshman", bestRank: 11, worstRank: "NR", summary: "A strong, versatile wing who projects as a three-and-D prospect (43.1% from three in EYBL). He can score inside and out, with the size, skill, and toughness NBA teams seek. He can create off the dribble and finish through contact. His mindset and tools scream long-term NBA role player with upside if his skill level keeps trending up.", nbaComp: "N/A" },
            { rank: 35, name: "Sergio De Larrea", position: "PG", school: "Spain", height: "6-6", weight: "175 lbs", wingspan: "6-7", class: "2005", bestRank: 17, worstRank: "NR", summary: "A combo guard with good size and nice feel for the game. He's an appealing mix of shooting (43.2% from three) and playmaking (27.6% assist percentage) for a wing. His ability to pass and make shots makes him a valuable combo/connector prospect, despite not being an explosive finisher.", nbaComp: "N/A" },
            { rank: 36, name: "Aday Mara", position: "C", school: "Michigan", height: "7-3", weight: "233 lbs", wingspan: "7-6", class: "Junior", bestRank: 22, worstRank: "NR", summary: "A talented passer and skilled offensive player. He's a skilled center with finesse and is more of a traditional big man. He projects to struggle defensively at the NBA level due to a lack of quickness and strength.", nbaComp: "Boban Marjanovic" },
            { rank: 37, name: "Milos Uzan", position: "PG", school: "Houston", height: "6-4", weight: "190 lbs", wingspan: "6-5", class: "Senior", bestRank: 24, worstRank: "NR", summary: "A true point guard with excellent size who plays both ends of the floor. He's a reliable, steady player who runs the show on offense.", nbaComp: "N/A" },
            { rank: 38, name: "Braden Smith", position: "PG", school: "Purdue", height: "6-0", weight: "175 lbs", wingspan: "6-3", class: "Senior", bestRank: 28, worstRank: "NR", summary: "A fearless scorer, playmaker, and defender who plays bigger than his size. He was a star in college and is fundamentally sound, making him a candidate to find a place in the league.", nbaComp: "Tyler Kolek, smaller Steve Blake" },
            { rank: 39, name: "Alex Karaban", position: "SF/PF", school: "UConn", height: "6-8", weight: "219 lbs", wingspan: "6-11", class: "Senior", bestRank: 27, worstRank: "NR", summary: "A forward with a clear NBA skill-set: great size and shooting ability. He's a heady player, an efficient finisher, and good cutter who scores within the flow of the offense. While not a dynamic athlete, his plug-and-play shot-making and professionalism are valued.", nbaComp: "Taller Landry Shamet, Sam Hauser" },
            { rank: 40, name: "Brayden Burries", position: "SG", school: "Arizona", height: "6-4", weight: "200 lbs", wingspan: "6-5", class: "Freshman", bestRank: 18, worstRank: "NR", summary: "A solid, skilled, and fundamentally sound guard who 'just knows how to play.' He is creative with sharp footwork and an impressive finishing/layup package. He's a shot-maker, especially off the dribble, with good body control and strength. His IQ and NBA-level scoring ability should translate well.", nbaComp: "N/A" },
            { rank: 41, name: "Patrick Ngongba II", position: "C", school: "Duke", height: "6-11", weight: "235 lbs", wingspan: "7-4", class: "Sophomore", bestRank: 13, worstRank: "NR", summary: "A workhorse in the lane who is not flashy but is effective and impactful. He's a playmaking big with excellent hands and patience around the basket, often converting driving layups. He projects as a useful frontcourt depth piece with a special feel for finishing plays and delivering assists.", nbaComp: "Mobile Adonal Foyle, Tony Bradley" },
            { rank: 42, name: "Dailyn Swain", position: "SG/SF", school: "Texas", height: "6-8", weight: "220 lbs", wingspan: "6-10", class: "Sophomore", bestRank: 36, worstRank: "NR", summary: "A versatile two-way wing with size, fluid movement, and high basketball IQ who projects well for the NBA's spacing. He thrives as a connector and transition playmaker, capable of pushing the ball and finishing with both hands. His defensive versatility is a major strength, as he can guard 1-3. His 'swing skill' is his shooting, which needs major work due to a lack of confidence, balance, and follow-through.", nbaComp: "N/A" },
            { rank: 43, name: "Solo Ball", position: "SG", school: "UConn", height: "6-4", weight: "190 lbs", wingspan: "6-6", class: "Junior", bestRank: 21, worstRank: "NR", summary: "A dynamic athlete who competes at a high level and can really shoot the rock. He is a high-scoring guard with a lot of fire.", nbaComp: "N/A" },
            { rank: 44, name: "Darrion Williams", position: "SF/PF", school: "NC State", height: "6-6", weight: "236 lbs", wingspan: "6-6", class: "Senior", bestRank: 33, worstRank: "NR", summary: "A fundamentally sound forward who impacts all aspects of the game. He has a great feel for the game and is a good passer.", nbaComp: "John Konchar, Kenrich Williams" },
            { rank: 45, name: "Jaland Lowe", position: "PG", school: "Kentucky", height: "6-3", weight: "162 lbs", wingspan: "6-6", class: "Junior", bestRank: 31, worstRank: "NR", summary: "A smooth and efficient lead guard who can run the show on offense and score from three levels.", nbaComp: "N/A" },
            { rank: 46, name: "Tomislav Ivisic", position: "C", school: "Illinois", height: "7-1", weight: "220 lbs", wingspan: "7-3", class: "Sophomore", bestRank: 35, worstRank: "NR", summary: "Zvonimir's twin brother is a 7-1' center with great size and a high skill level. He's a very good passer and a legit floor spacer who can 'really shoot the rock.' He rebounds well and defends the lane. While a bit heavy and not as smooth of a mover as his brother, he has great strength and toughness inside.", nbaComp: "N/A" },
            { rank: 47, name: "Nate Bittle", position: "C", school: "Oregon", height: "7-0", weight: "250 lbs", wingspan: "7-6", class: "Senior", bestRank: 34, worstRank: "NR", summary: "A wiry, mobile big who can hit the three and defend the rim. He's looking to get back into draft discussions after an injury-plagued season.", nbaComp: "Quentin Post" },
            { rank: 48, name: "Darren Harris", position: "SG/SF", school: "Duke", height: "6-5", weight: "195 lbs", wingspan: "6-7", class: "Sophomore", bestRank: 27, worstRank: "NR", summary: "A sharp-shooting guard who can score from three levels and plays a nice all-around game. He is not overly explosive but has good size and strength.", nbaComp: "N/A" },
            { rank: 49, name: "Andrej Kostic", position: "SG/SF", school: "Kansas State", height: "6-6", weight: "195 lbs", wingspan: "6-9", class: "2006", bestRank: 24, worstRank: "NR", summary: "A crafty scorer and skilled playmaker with good size on the wing.", nbaComp: "N/A" },
            { rank: 50, name: "Ognjen Srzentic", position: "SG/SF", school: "Mega Basket, Serbia", height: "6-7", weight: "190 lbs", wingspan: "6-9", class: "2007", bestRank: 25, worstRank: "NR", summary: "A scoring guard/wing with a clean shooting stroke, ball-handling to create, and clear range/confidence. He was named MVP of ANGT Istanbul, averaging 22.0 points. He looks set for a key role in the main squad of a club that consistently produces draft picks.", nbaComp: "N/A" },
            { rank: 51, name: "Zuby Ejiofor", position: "PF/C", school: "St. John’s", height: "6-9", weight: "240 lbs", wingspan: "7-1", class: "Junior", bestRank: 34, worstRank: "NR", summary: "A burly big man whose primary attributes are not specified beyond his physical profile.", nbaComp: "N/A" },
            { rank: 52, name: "Hannes Steinbach", position: "PF/SF", school: "Washington", height: "6-10", weight: "185 lbs", wingspan: "6-11", class: "2006", bestRank: 26, worstRank: "NR", summary: "A combo forward who gives defenses trouble with an old-school, back-to-the-basket post offense, utilizing patience, footwork, and touch. He occasionally flashes shooting range, face-up moves, and vertical pop at the rim. He led Germany to a Silver medal at the U19 World Cup.", nbaComp: "N/A" },
            { rank: 53, name: "Jacob Cofie", position: "PF", school: "USC", height: "6-10", weight: "230 lbs", wingspan: "7-0", class: "Sophomore", bestRank: 23, worstRank: "NR", summary: "A forward who had a breakout freshman season and looks like a future NBA player. He is so talented, but just super inconsistent motor.", nbaComp: "N/A" },
            { rank: 54, name: "Motiejus Krivas", position: "C", school: "Arizona", height: "7-2", weight: "260 lbs", wingspan: "7-2", class: "Junior", bestRank: 27, worstRank: "NR", summary: "A rock-solid center who rebounds the ball and defends in the lane. He is skilled with the ball but is lacking in athleticism.", nbaComp: "N/A" },
            { rank: 55, name: "Neoklis Avdalas", position: "SG/SF", school: "Virginia Tech", height: "6-9", weight: "187 lbs", wingspan: "6-8", class: "Freshman", bestRank: 26, worstRank: "NR", summary: "A big guard/wing with a nice offensive package and NBA-level scoring ability.", nbaComp: "N/A" },
            { rank: 56, name: "Joson Sanon", position: "SG", school: "St. John’s", height: "6-6", weight: "200 lbs", wingspan: "6-8", class: "Sophomore", bestRank: 29, worstRank: "NR", summary: "A powerful, big combo guard with an NBA frame and an aggressive game. He has nice passing instincts, good handles, and can hit the three-point shot.", nbaComp: "Ja’Kobe Walter" },
            { rank: 57, name: "Johann Grunloh", position: "PF/C", school: "Virginia", height: "6-10", weight: "220 lbs", wingspan: "7-0", class: "2005", bestRank: 37, worstRank: "NR", summary: "A floor-spacing big forward with a high skill level and good size but average athleticism.", nbaComp: "N/A" },
            { rank: 58, name: "Donnie Freeman", position: "PF", school: "Syracuse", height: "6-9", weight: "205 lbs", wingspan: "6-10", class: "Sophomore", bestRank: 29, worstRank: "NR", summary: "A fundamentally sound forward with a strong, athletic frame and a smooth mid-range game. He is on an awesome, rapidly improving trajectory.", nbaComp: "Marcus Morris" },
            { rank: 59, name: "Andrej Stojakovic", position: "SG/SF", school: "Illinois", height: "6-7", weight: "205 lbs", wingspan: "6-9", class: "Junior", bestRank: 4, worstRank: "NR", summary: "The son of Peja, he is a silky smooth three-point shooter and a high-level competitor who is starting to put his game together.", nbaComp: "N/A" },
            { rank: 60, name: "Tyler Harris", position: "SF", school: "Vanderbilt", height: "6-9", weight: "200 lbs", wingspan: "6-10", class: "Junior", bestRank: 18, worstRank: "NR", summary: "A sweet-shooting wing with good size and NBA-level tools.", nbaComp: "N/A" },
            { rank: 61, name: "Miikka Muurinen", position: "PF", school: "Partizan Belgrade, Finland", height: "6-11", weight: "190 lbs", wingspan: "7-3", class: "2007", bestRank: "NR", worstRank: "NR", summary: "A skilled big man with awesome mobility and big-time offensive talent. He has a modern game and looks the part of a future lottery pick (in 2027).", nbaComp: "Jan Vesely, skinnier John Collins" },
            { rank: 62, name: "Flory Bidunga", position: "C", school: "Kansas", height: "6-9", weight: "225 lbs", wingspan: "7-2.5", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "A long-armed center with elite physical tools and athleticism. He's a powerhouse, super quick, fluid athlete who dominates around the rim and on the boards. He's a ferocious finisher and high-level rim runner. He needs to improve his offensive range and foul discipline.", nbaComp: "Charles Bassey, Orlando Robinson" },
            { rank: 63, name: "Mackenzie Mgbako", position: "SF/PF", school: "Texas A&M", height: "6-9", weight: "216 lbs", wingspan: "6-10", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A sweet-shooting wing with good size, making him a highly projectable floor-spacing forward. He excels at shooting off the catch and the dribble and has a complete game. He has improved his finishing inside, but questions remain about his lost athleticism/explosiveness and limited defensive impact.", nbaComp: "Saddiq Bey, Emoni Bates" },
            { rank: 64, name: "Baye Ndongo", position: "PF", school: "Georgia Tech, Senegal", height: "6-9", weight: "225 lbs", wingspan: "7-2", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A high-level athlete and defender with an explosive, rugged frame for the NBA. He's a strong paint protector, dynamic rim runner, and high-motor rebounder who offers switchability. He still needs to polish his ball skills and improve his passing reads, but his relentless energy is a major strength.", nbaComp: "Trevor Booker, Gani Lawal, Pascal Siakam (early traits)" },
            { rank: 65, name: "Michael Ruzic", position: "PF", school: "Croatia", height: "7-0", weight: "221 lbs", wingspan: "7-0.75", class: "2006", bestRank: "NR", worstRank: "NR", summary: "A smooth-scoring combo forward with a lot of offensive upside. He shoots the ball extremely well and plays a modern floor-spacing game. He'll need to gain strength and improve his defense.", nbaComp: "Ersan İlyasova" },
            { rank: 66, name: "Jaron Pierre Jr.", position: "SG", school: "SMU", height: "6-6", weight: "188 lbs", wingspan: "NA", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A high-flying and high-scoring small-school talent.", nbaComp: "N/A" },
            { rank: 67, name: "Magoon Gwath", position: "C", school: "San Diego State", height: "7-0", weight: "205 lbs", wingspan: "7-3", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "A very intriguing big man with a unique mix of shot blocking, great height, three-point shooting, and very good mobility for his size.", nbaComp: "N/A" },
            { rank: 68, name: "Hudson Greer", position: "SG", school: "Creighton", height: "6-6", weight: "190 lbs", wingspan: "6-6", class: "Freshman", bestRank: "NR", worstRank: "NR", summary: "A talented wing best playing off the ball, scoring from the perimeter or on cuts to the rim. He has fluid athleticism and a solid frame. He possesses a high basketball IQ and great feel for finding open teammates, and he finishes well with layups and floaters.", nbaComp: "N/A" },
            { rank: 69, name: "Amarion Dickerson", position: "SF", school: "USC", height: "6-7", weight: "197 lbs", wingspan: "6-8", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A combo guard who transferred to Robert Morris. Detailed 2026 NBA Draft scouting reports are unavailable, but he was listed as a high-ranked transfer portal prospect.", nbaComp: "N/A" },
            { rank: 70, name: "Jackson Shelstad", position: "PG", school: "Oregon", height: "6-0", weight: "175 lbs", wingspan: "6-3", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A point guard who is electric with the ball in his hands, combining scoring prowess and playmaking ability. He lacks ideal size/height but compensates with a strong frame, toughness, and grit.", nbaComp: "N/A" },
            { rank: 71, name: "DJ Wagner", position: "SG", school: "Arkansas", height: "6-3", weight: "190 lbs", wingspan: "6-5", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A 'bucket' who can score the ball, create for others and carry his team on offense. He lacks ideal size for a two-guard and needs to be more consistent shooting from downtown.", nbaComp: "Jared Butler" },
            { rank: 72, name: "Josh Dix", position: "SG", school: "Creighton", height: "6-6", weight: "210 lbs", wingspan: "6-8", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A lethal three-point shooter with good size and solid athleticism, a solid blueprint for an NBA player.", nbaComp: "N/A" },
            { rank: 73, name: "Silas Demary Jr.", position: "PG/SG", school: "UConn", height: "6-4", weight: "195 lbs", wingspan: "6-6", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A well-built guard with all the tools for the NBA. He has rounded out his game, showing vast improvements shooting the ball from outside, and his arrow is pointing up.", nbaComp: "N/A" },
            { rank: 74, name: "Jalil Bethea", position: "SG", school: "Alabama", height: "6-4", weight: "190 lbs", wingspan: "6-8", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "An ultra-talented two-guard who can score in bunches, has deep range, and possesses bounce/above-the-rim ability. He is slight of frame and must add strength to guard at the NBA level.", nbaComp: "N/A" },
            { rank: 75, name: "Donovan Dent", position: "PG", school: "UCLA", height: "6-2", weight: "170 lbs", wingspan: "NA", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A bit undersized but a crafty playmaker and finisher.", nbaComp: "N/A" },
            { rank: 76, name: "Jasper Johnson", position: "PG/SG", school: "Kentucky", height: "6-5", weight: "170 lbs", wingspan: "6-8", class: "Freshman", bestRank: "NR", worstRank: "NR", summary: "A wiry lead guard with a quick first step and a nice scoring package. He has potent shot-making and touch shots, and could be an instant-offense type of player depending on his physical development and playmaking.", nbaComp: "N/A" },
            { rank: 77, name: "Hugo Facorat", position: "PF", school: "France", height: "6-10", weight: "200 lbs", wingspan: "7-1", class: "2007", bestRank: "NR", worstRank: "NR", summary: "A skilled combo forward with great height and length. He has a lot of upside but is raw and needs to get stronger to defend in the NBA.", nbaComp: "N/A" },
            { rank: 78, name: "Ben Henshall", position: "SG", school: "Perth, NBL", height: "6-5", weight: "198 lbs", wingspan: "6-7", class: "2004", bestRank: "NR", worstRank: "NR", summary: "A solid SG prospect with a nice-looking three-point shot and a good pull-up game.", nbaComp: "N/A" },
            { rank: 79, name: "Nolan Winter", position: "PF/C", school: "Wisconsin", height: "6-11", weight: "235 lbs", wingspan: "7-0", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A switch big who is a Big Ten standout, coming off a breakout sophomore campaign where he averaged 9.4 points and 5.8 rebounds. He led the Big Ten in two-point field goal percentage (71.5%) and showed athleticism and soaring finishes at the rim.", nbaComp: "N/A" },
            { rank: 80, name: "Tarris Reed", position: "C", school: "UConn", height: "6-10", weight: "260 lbs", wingspan: "7-5", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A burly big man who has really good footwork and is a difference-maker in the paint.", nbaComp: "N/A" },
            { rank: 81, name: "PJ Haggerty", position: "PG", school: "Kansas State", height: "6-3", weight: "195 lbs", wingspan: "6-7", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A high-scoring guard who can play on or off the ball.", nbaComp: "N/A" },
            { rank: 82, name: "Cameron Carr", position: "SG", school: "Baylor", height: "6-7", weight: "170 lbs", wingspan: "7-2", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A long, lanky guard with a picture-perfect jumper. He needs to add strength.", nbaComp: "N/A" },
            { rank: 83, name: "Zvonimir Ivisic", position: "C", school: "Illinois, Croatia", height: "7-3", weight: "245 lbs", wingspan: "NA", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "Tomislav's twin brother ('Big Z') is a 7-3' stretch-big who loves to operate on the perimeter. He has good ball skills and great physical tools but needs continued development and to get stronger.", nbaComp: "Andrea Bargnani" },
            { rank: 84, name: "Tucker DeVries", position: "SG/SF", school: "Indiana", height: "6-7", weight: "210 lbs", wingspan: "NA", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A sweet-shooting big guard with deep range and a very efficient game.", nbaComp: "N/A" },
            { rank: 85, name: "Jevon Porter", position: "PF/C", school: "Missouri", height: "6-11", weight: "235 lbs", wingspan: "6-11", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "Missouri combo big who was previously projected as a potential second-round pick in the 2024 NBA Draft. He is being monitored as a returning prospect in college basketball.", nbaComp: "N/A" },
            { rank: 86, name: "Joshua Jefferson", position: "PF", school: "Iowa State", height: "6-9", weight: "240 lbs", wingspan: "6-10", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A big-bodied forward who plays an impressive all-around game.", nbaComp: "N/A" },
            { rank: 87, name: "Kwame Evans Jr.", position: "SF", school: "Oregon", height: "6-9", weight: "200 lbs", wingspan: "7-0", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A jumbo wing with great length and mobility who can defend all over the court. His offensive game is a work in progress, and he struggles to shoot consistently.", nbaComp: "N/A" },
            { rank: 88, name: "Tobi Lawal", position: "PF", school: "Virginia Tech", height: "6-8", weight: "215 lbs", wingspan: "NA", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A forward whose calling card is 'freakish leaping ability,' with a reported 49.5-inch vertical. For him to lift his team and build his draft stock, he needs to make more than a physical leap.", nbaComp: "N/A" },
            { rank: 89, name: "Alvaro Folgueiras", position: "PF", school: "Iowa, Spain", height: "6-9", weight: "215 lbs", wingspan: "7-6", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A floor-spacing big man who plays a crafty game but does not have ideal athleticism.", nbaComp: "Luis Scola" },
            { rank: 90, name: "Xaivian Lee", position: "PG", school: "Florida, Canada", height: "6-4", weight: "171 lbs", wingspan: "6-4", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A crafty guard who can shoot the rock and score from three levels. A fun player to watch.", nbaComp: "N/A" },
            { rank: 91, name: "Momo Faye", position: "PF/C", school: "Paris Basket, France", height: "6-9", weight: "223 lbs", wingspan: "7-4", class: "2005", bestRank: "NR", worstRank: "NR", summary: "He possesses the physical tools, defensive versatility, and high motor that NBA teams value. He is an agile and physical presence, an effective rim protector, and a natural lob threat/rim-runner. His offensive skill set is raw.", nbaComp: "N/A" },
            { rank: 92, name: "JJ Starling", position: "SG", school: "Syracuse", height: "6-4", weight: "180 lbs", wingspan: "6-9", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A big combo/scoring guard who is streaky shooting the ball but can fill it up once he gets going.", nbaComp: "Rashad McCants" },
            { rank: 93, name: "KJ Lewis", position: "SG", school: "Georgetown", height: "6-4", weight: "205 lbs", wingspan: "NA", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A good athlete with a downhill style, NBA-level strength/size, and is a standout defender, but he's not a great shot-maker.", nbaComp: "N/A" },
            { rank: 94, name: "Trey Kaufman-Renn", position: "PF", school: "Purdue", height: "6-9", weight: "230 lbs", wingspan: "NA", class: "Senior", bestRank: "NR", worstRank: "NR", summary: "A key player for Purdue, named to the Preseason All-Big Ten First Team. His inclusion on the league's top team suggests strong draft buzz.", nbaComp: "N/A" },
            { rank: 95, name: "Henri Veesaar", position: "C", school: "North Carolina, Estonia", height: "7-0", weight: "225 lbs", wingspan: "NA", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A glue-guy center who does all the dirty work, rebounds, defends well, and can also step out and hit the outside shot. He is a high-energy player.", nbaComp: "Chris Anderson" },
            { rank: 96, name: "Tyrone Riley", position: "SF", school: "San Francisco", height: "6-6", weight: "190 lbs", wingspan: "NA", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "A talented wing with nice above-the-rim athletic ability and a knack for scoring the ball. He is praised as a good off-the-ball mover with a feel for finding space in the defense.", nbaComp: "Josh Hart, Terance Mann" },
            { rank: 97, name: "Robert Wright", position: "PG", school: "BYU", height: "6-0", weight: "183 lbs", wingspan: "6-3", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "A dynamic player and 'jitterbug' who is a true floor general with good court vision and high feel. He has an incredible first step and a knack for getting into the lane and scoring.", nbaComp: "Jalen Pickett, poor man’s Peyton Pritchard" },
            { rank: 98, name: "Morez Johnson", position: "PF/C", school: "Michigan", height: "6-9", weight: "220 lbs", wingspan: "NA", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "Undersized big, mobile that loves to rebound and defend but has scoring question marks at the next level. His entire offense is built around finishing through and over defenders.", nbaComp: "N/A" },
            { rank: 99, name: "Xavier Booker", position: "PF", school: "UCLA", height: "6-11", weight: "245 lbs", wingspan: "7-5", class: "Junior", bestRank: "NR", worstRank: "NR", summary: "A high-upside gamble on elite physical tools, Booker is a springy 6'11' forward who has the potential to become a true stretch-big. The big lefty possesses fluidity and a developing perimeter-oriented game.", nbaComp: "Doup Reath" },
            { rank: 100, name: "Sadiq White", position: "SF", school: "Syracuse", height: "6-9", weight: "250 lbs", wingspan: "7-3", class: "Sophomore", bestRank: "NR", worstRank: "NR", summary: "A super-athletic, high-motor wing whose game is built on defense and transition scoring. White is a versatile defender with a reported seven-foot wingspan, allowing him to cover a wide range of positions.", nbaComp: "Derrick Jones Jr., higher-ceiling Torrey Craig" }
        ];

        document.addEventListener('DOMContentLoaded', function () {
            feather.replace();
            
            // Populate table
            const prospectsList = document.getElementById('prospects-list');
            prospects.forEach(prospect => {
                const row = document.createElement('tr');
                row.className = 'prospect-row';
                row.innerHTML = `
                    <td class="px-6 py-4 font-semibold text-gray-900">${prospect.rank}</td>
                    <td class="px-6 py-4">
                        <div class="text-base font-bold text-gray-900">${prospect.name}</div>
                        <div class="text-sm text-gray-500">${prospect.height} | ${prospect.weight}</div>
                    </td>
                    <td class="px-6 py-4 text-sm text-gray-700 hidden sm:table-cell">${prospect.position}</td>
                    <td class="px-6 py-4 text-sm text-gray-700 hidden lg:table-cell">${prospect.school}</td>
                    <td class="px-6 py-4 text-center">
                        <a href="#" class="profile-link" data-rank="${prospect.rank}">View Profile</a>
                    </td>
                `;
                prospectsList.appendChild(row);
            });

            // Modal functionality
            const modal = document.getElementById('player-modal');
            const modalTitle = document.getElementById('modal-title');
            const modalContent = document.getElementById('modal-content');
            const closeModalBtn = document.getElementById('close-modal');

            function showPlayerModal(rank) {
                const prospect = prospects.find(p => p.rank === parseInt(rank));
                if (!prospect) return;

                modalTitle.innerHTML = `#${prospect.rank} ${prospect.name}`;
                modalContent.innerHTML = `
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <h4 class="font-bold text-gray-700 mb-2">Player Information</h4>
                            <ul class="space-y-1 text-sm text-gray-600">
                                <li><span class="font-semibold">Position:</span> ${prospect.position}</li>
                                <li><span class="font-semibold">School/Team:</span> ${prospect.school}</li>
                                <li><span class="font-semibold">Class:</span> ${prospect.class}</li>
                                <li><span class="font-semibold">Height:</span> ${prospect.height}</li>
                                <li><span class="font-semibold">Weight:</span> ${prospect.weight}</li>
                                <li><span class="font-semibold">Wingspan:</span> ${prospect.wingspan}</li>
                            </ul>
                        </div>
                        <div>
                            <h4 class="font-bold text-gray-700 mb-2">Draft Stock</h4>
                            <ul class="space-y-1 text-sm text-gray-600">
                                <li><span class="font-semibold">Best Rank:</span> ${prospect.bestRank}</li>
                                <li><span class="font-semibold">Worst Rank:</span> ${prospect.worstRank}</li>
                                <li><span class="font-semibold">NBA Comparison:</span> ${prospect.nbaComp}</li>
                            </ul>
                        </div>
                    </div>
                    <div class="mt-6">
                        <h4 class="font-bold text-gray-700 mb-2">Scouting Report</h4>
                        <p class="text-sm text-gray-600 leading-relaxed">${prospect.summary}</p>
                    </div>
                `;
                modal.classList.add('modal-open');
                // Re-render feather icons for any that might be in the modal (none in this case, but good practice)
                feather.replace();
            }

            function closePlayerModal() {
                modal.classList.remove('modal-open');
            }

            // Event listeners for modal
            document.querySelectorAll('.profile-link').forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    showPlayerModal(e.target.dataset.rank);
                });
            });

            closeModalBtn.addEventListener('click', closePlayerModal);
            modal.addEventListener('click', (e) => {
                if (e.target === modal) {
                    closePlayerModal();
                }
            });

            // Search functionality
            const searchInput = document.getElementById('search-input');
            searchInput.addEventListener('input', (e) => {
                const searchTerm = e.target.value.toLowerCase();
                document.querySelectorAll('.prospect-row').forEach(row => {
                    const playerName = row.querySelector('td:nth-child(2)').textContent.toLowerCase();
                    if (playerName.includes(searchTerm)) {
                        row.style.display = '';
                    } else {
                        row.style.display = 'none';
                    }
                });
            });
        });

        // Vanta.js Background
        VANTA.GLOBE({
            el: "#vanta-bg",
            mouseControls: true,
            touchControls: true,
            gyroControls: false,
            minHeight: 200.00,
            minWidth: 200.00,
            scale: 1.00,
            scaleMobile: 1.00,
            color: 0xff0000,
            backgroundColor: 0xf7f7f7
        });

    </script>
</body>
</html>






 
