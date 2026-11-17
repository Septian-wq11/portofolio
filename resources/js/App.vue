<template>
  <div class="relative min-h-screen bg-[#0a0a0c] text-[#f4f4f5] overflow-x-hidden selection:bg-[#d92332] selection:text-white font-sans antialiased">
    
    <!-- THEATRICAL AMBIENT LIGHTING -->
    <div class="fixed inset-0 pointer-events-none z-0 overflow-hidden">
      <!-- Center Crimson Atmospheric Glow behind PORTFOLIO & Subject -->
      <div class="absolute -top-[10%] left-1/2 -translate-x-1/2 w-[90vw] max-w-[1100px] h-[750px] rounded-full bg-[radial-gradient(circle_at_center,rgba(185,25,38,0.30)_0%,rgba(10,10,12,0)_72%)] blur-[100px]"></div>
      <!-- Side Crimson Fill Glows -->
      <div class="absolute top-[35%] -left-[10%] w-[450px] h-[450px] rounded-full bg-[radial-gradient(circle_at_center,rgba(185,25,38,0.12)_0%,rgba(10,10,12,0)_70%)] blur-[120px]"></div>
      <div class="absolute bottom-[8%] -right-[8%] w-[550px] h-[550px] rounded-full bg-[radial-gradient(circle_at_center,rgba(143,18,29,0.15)_0%,rgba(10,10,12,0)_70%)] blur-[140px]"></div>
      <!-- Fine Texture Grid -->
      <div class="absolute inset-0 bg-[radial-gradient(#272732_0.75px,transparent_0.75px)] [background-size:24px_24px] opacity-15"></div>
    </div>

    <!-- SINGLE CLEAN EDITORIAL NAVIGATION BAR (Responsive, no collisions!) -->
    <header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 backdrop-blur-md bg-[#0a0a0c]/90 border-b border-zinc-900/80">
      <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-10 h-16 flex items-center justify-between gap-4 select-none">
        
        <!-- Left: Roles Labels (Compact, responsive) -->
        <div class="flex flex-col shrink-0">
          <span class="text-[10px] sm:text-[11px] font-bold text-[#d92332] tracking-[0.22em] uppercase leading-tight">
            UX DESIGNER & FRONTEND DEV
          </span>
          <span class="text-[9px] sm:text-[10px] font-semibold text-zinc-400 tracking-[0.2em] uppercase leading-tight mt-0.5">
            SYSTEM ANALYST
          </span>
        </div>

        <!-- Center: Desktop Navigation Links (Visible on lg+, hidden on mobile/tablet to prevent collision) -->
        <div class="hidden lg:flex items-center gap-6 xl:gap-8 text-[11px] font-bold tracking-[0.2em] uppercase text-zinc-400">
          <a href="#about" class="hover:text-white transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#d92332] hover:after:w-full after:transition-all">About</a>
          <a href="#projects" class="hover:text-white transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#d92332] hover:after:w-full after:transition-all">Projects</a>
          <a href="#process" class="hover:text-white transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#d92332] hover:after:w-full after:transition-all">Process</a>
          <a href="#experience" class="hover:text-white transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#d92332] hover:after:w-full after:transition-all">Experience</a>
          <a href="#achievements" class="hover:text-white transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#d92332] hover:after:w-full after:transition-all">Awards</a>
          <a href="#contact" class="hover:text-white transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#d92332] hover:after:w-full after:transition-all">Contact</a>
        </div>

        <!-- Right: Available for Freelance with Sparkle (Shrink-0 to avoid crushing) -->
        <div class="hidden sm:flex items-center gap-2 shrink-0">
          <a href="#contact" class="flex items-center gap-2 group cursor-pointer">
            <span class="text-[10px] sm:text-[11px] font-bold tracking-[0.2em] text-zinc-300 group-hover:text-white transition-colors uppercase whitespace-nowrap">
              AVAILABLE FOR FREELANCE
            </span>
            <Sparkle class="w-3.5 h-3.5 text-[#d92332] fill-current group-hover:scale-110 transition-transform shrink-0" />
          </a>
        </div>

        <!-- Mobile & Tablet Menu Hamburger Button (Visible on < lg) -->
        <button 
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="lg:hidden p-2 rounded-xs text-zinc-300 hover:text-white hover:bg-zinc-900 transition-colors cursor-pointer shrink-0"
          aria-label="Toggle Menu"
        >
          <svg v-if="!mobileMenuOpen" class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/></svg>
          <svg v-else class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
        </button>
      </nav>

      <!-- Mobile & Tablet Dropdown Navigation -->
      <div v-show="mobileMenuOpen" class="lg:hidden bg-[#0e0e12]/95 border-b border-zinc-800 backdrop-blur-xl px-6 py-5 space-y-4 shadow-2xl">
        <a @click="mobileMenuOpen = false" href="#about" class="block py-1 text-xs font-bold tracking-widest text-zinc-300 hover:text-[#d92332] uppercase">About & Skills</a>
        <a @click="mobileMenuOpen = false" href="#projects" class="block py-1 text-xs font-bold tracking-widest text-zinc-300 hover:text-[#d92332] uppercase">Projects</a>
        <a @click="mobileMenuOpen = false" href="#process" class="block py-1 text-xs font-bold tracking-widest text-zinc-300 hover:text-[#d92332] uppercase">Work Process</a>
        <a @click="mobileMenuOpen = false" href="#experience" class="block py-1 text-xs font-bold tracking-widest text-zinc-300 hover:text-[#d92332] uppercase">Experience</a>
        <a @click="mobileMenuOpen = false" href="#achievements" class="block py-1 text-xs font-bold tracking-widest text-zinc-300 hover:text-[#d92332] uppercase">Achievements</a>
        <a @click="mobileMenuOpen = false" href="#contact" class="block py-1 text-xs font-bold tracking-widest text-zinc-300 hover:text-[#d92332] uppercase">Contact</a>
        <div class="pt-2">
          <a @click="mobileMenuOpen = false" href="#contact" class="block text-center w-full py-2.5 rounded-full bg-[#d92332] text-white text-xs font-bold tracking-widest uppercase shadow-md">
            Let's Work Together
          </a>
        </div>
      </div>
    </header>

    <!-- MAIN PAGE CONTAINER -->
    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-10 pt-20 pb-8 flex flex-col min-h-screen justify-between">
      
      <!-- HERO SECTION -->
      <section class="relative pt-2 sm:pt-6 pb-12 sm:pb-20 overflow-visible">
        
        <!-- MASSIVE CONDENSED BACKGROUND TYPOGRAPHY: "PORTFOLIO" -->
        <div class="w-full text-center overflow-hidden pointer-events-none select-none relative z-10">
          <h1 class="font-display font-bold text-[21vw] sm:text-[19vw] md:text-[17vw] lg:text-[15.5rem] xl:text-[18rem] leading-[0.74] tracking-tight uppercase text-[#991420] transition-all duration-700">
            PORTFOLIO
          </h1>
        </div>

        <!-- FOREGROUND HERO STAGE (Photo rises directly into "PORTFOLIO" letters!) -->
        <div class="relative z-20 -mt-14 sm:-mt-24 md:-mt-36 lg:-mt-44 xl:-mt-56 grid grid-cols-1 lg:grid-cols-12 gap-8 items-end">
          
          <!-- LEFT COLUMN: Identity, Cursive Greeting & Bio (Desktop: 4 cols) -->
          <div class="lg:col-span-4 flex flex-col justify-end space-y-4 pt-2 sm:pt-0 relative z-30 text-center lg:text-left order-2 lg:order-1">
            <!-- Script Cursive "Hello, I'm" -->
            <div class="font-script text-[#d92332] text-3xl sm:text-4xl -rotate-3 select-none origin-bottom-left -mb-1">
              Hello, I'm
            </div>

            <!-- Big Condensed Name -->
            <div class="space-y-0 select-none">
              <h2 class="font-display font-bold text-6xl sm:text-7xl lg:text-7xl xl:text-[5.5rem] text-white tracking-tight leading-[0.88] uppercase drop-shadow-md">
                SEPTIAN
              </h2>
              <h2 class="font-display font-bold text-6xl sm:text-7xl lg:text-7xl xl:text-[5.5rem] text-white tracking-tight leading-[0.88] uppercase drop-shadow-md">
                LISTIA
              </h2>
            </div>

            <!-- Roles Subtitle -->
            <div class="pt-1">
              <div class="text-xs sm:text-[12px] font-bold text-[#d92332] tracking-[0.2em] uppercase">
                UX DESIGNER • FRONTEND DEVELOPER • SYSTEM ANALYST
              </div>
            </div>

            <!-- Exact Bio from Previous Portfolio -->
            <p class="text-xs sm:text-[13px] text-zinc-300 font-normal leading-relaxed max-w-md mx-auto lg:mx-0 drop-shadow-sm">
              Mahasiswa Sistem Informasi UPN Veteran Jawa Timur berprestasi nasional yang berfokus membangun produk digital yang intuitif, estetik, dan berorientasi solusi bisnis nyata melalui pendekatan <strong class="text-white font-semibold">Design Thinking</strong> dan rekayasa web modern.
            </p>

            <!-- Availability & Location Indicator -->
            <div class="pt-2 flex flex-wrap justify-center lg:justify-start items-center gap-3 text-[11px] font-semibold tracking-wider text-zinc-400">
              <div class="flex items-center gap-2">
                <div class="w-3.5 h-3.5 rounded-full border border-[#d92332] flex items-center justify-center">
                  <span class="w-1.5 h-1.5 rounded-full bg-[#d92332] animate-pulse"></span>
                </div>
                <span class="uppercase tracking-widest text-zinc-300">AVAILABLE FOR HIRE</span>
              </div>
              <span class="text-zinc-600">•</span>
              <span class="text-zinc-400">SURABAYA, ID</span>
            </div>
          </div>

          <!-- CENTER COLUMN: Septian's Real Cutout Photo (Directly Overlapping PORTFOLIO letters!) (Desktop: 5 cols) -->
          <div class="lg:col-span-5 relative flex flex-col items-center justify-end z-20 order-1 lg:order-2">
            
            <!-- Scaled Portrait Container (Naturally sized without empty top air) -->
            <div class="relative w-[280px] sm:w-[380px] md:w-[440px] lg:w-[480px] xl:w-[540px] aspect-square flex items-end justify-center select-none">
              
              <!-- Ambient Crimson Glow behind Portrait -->
              <div class="absolute inset-0 bg-radial from-[#d92332]/35 via-transparent to-transparent blur-3xl pointer-events-none -z-10"></div>

              <!-- REAL CUTOUT PORTRAIT PHOTO OVERLAPPING "PORTFOLIO" -->
              <img 
                :src="profileImg || './FotoProfile.png'" 
                alt="Septian Listia Tri Cahyo" 
                class="w-full h-full object-contain object-bottom filter drop-shadow-[0_20px_45px_rgba(0,0,0,0.95)] contrast-105 select-none relative z-20 transition-transform duration-500 hover:scale-[1.02]" 
              />

              <!-- FLOATING MOTTO BADGE (Beside Shoulder as in Reference) -->
              <div class="absolute top-[45%] -right-2 sm:-right-6 lg:-right-8 flex items-center gap-2.5 max-w-[160px] select-none z-30">
                <div class="w-7 h-7 shrink-0 rounded-full bg-[#18181f] border border-[#d92332]/60 flex items-center justify-center text-[#d92332] shadow-xl">
                  <Sparkle class="w-3.5 h-3.5 fill-current" />
                </div>
                <p class="text-[11px] text-zinc-400 font-normal leading-tight italic drop-shadow-md">
                  Turning ideas into powerful digital experiences.
                </p>
              </div>

            </div>
          </div>

          <!-- RIGHT COLUMN: Stacked Statistics from Original Portfolio (Desktop: 3 cols) -->
          <div class="lg:col-span-3 flex flex-row lg:flex-col justify-around lg:justify-end lg:items-end gap-6 sm:gap-10 pb-4 select-none relative z-30 order-3">
            <!-- Stat 1 -->
            <div class="text-center lg:text-right">
              <div class="font-display font-bold text-4xl sm:text-5xl lg:text-6xl text-[#d92332] leading-none tracking-tight drop-shadow-md">
                5+
              </div>
              <div class="text-[10px] sm:text-[11px] font-semibold tracking-[0.2em] text-zinc-400 uppercase mt-1 leading-snug">
                NATIONAL<br class="hidden lg:block"/> AWARDS
              </div>
            </div>

            <!-- Stat 2 -->
            <div class="text-center lg:text-right">
              <div class="font-display font-bold text-4xl sm:text-5xl lg:text-6xl text-[#d92332] leading-none tracking-tight drop-shadow-md">
                7+
              </div>
              <div class="text-[10px] sm:text-[11px] font-semibold tracking-[0.2em] text-zinc-400 uppercase mt-1 leading-snug">
                FEATURED<br class="hidden lg:block"/> PROJECTS
              </div>
            </div>

            <!-- Stat 3 -->
            <div class="text-center lg:text-right">
              <div class="font-display font-bold text-4xl sm:text-5xl lg:text-6xl text-[#d92332] leading-none tracking-tight drop-shadow-md">
                5+
              </div>
              <div class="text-[10px] sm:text-[11px] font-semibold tracking-[0.2em] text-zinc-400 uppercase mt-1 leading-snug">
                ROLES &<br class="hidden lg:block"/> MENTORING
              </div>
            </div>
          </div>

        </div>
      </section>

      <!-- SECTION 2: SELECTED PROJECTS (HORIZONTAL SCROLL / CAROUSEL TO PREVENT STACKING) -->
      <section id="projects" class="py-12 sm:py-16 border-t border-zinc-900/90 scroll-mt-20">
        
        <!-- Section Header with Category Tabs & Carousel Navigation Buttons -->
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-4 mb-6 sm:mb-8">
          <div>
            <span class="text-[10px] font-bold text-[#d92332] tracking-[0.26em] uppercase">FEATURED PORTFOLIO</span>
            <h2 class="text-base sm:text-xl font-bold tracking-[0.2em] text-white uppercase mt-0.5">
              SELECTED PROJECTS & CASE STUDIES
            </h2>
          </div>

          <div class="flex items-center gap-3">
            <!-- Category Tabs -->
            <div class="flex flex-wrap items-center gap-1.5 text-[10px] font-mono">
              <button 
                v-for="cat in projectCategories" 
                :key="cat.id"
                @click="setCategory(cat.id)"
                :class="activeCategory === cat.id ? 'bg-[#d92332] text-white border-[#d92332]' : 'bg-[#121216] text-zinc-400 hover:text-white border-zinc-800'"
                class="px-3 py-1.5 rounded-xs border transition-colors cursor-pointer uppercase tracking-wider"
              >
                {{ cat.label }}
              </button>
            </div>

            <!-- Carousel Prev & Next Arrows (Desktop) -->
            <div class="hidden sm:flex items-center gap-2 pl-2 border-l border-zinc-800">
              <button 
                @click="scrollProjects('prev')" 
                class="w-8 h-8 rounded-full border border-zinc-800 bg-[#121216] hover:border-[#d92332] hover:text-white text-zinc-400 flex items-center justify-center transition-colors cursor-pointer shadow-sm"
                title="Scroll Sebelumnya"
                aria-label="Previous Projects"
              >
                <ChevronLeft class="w-4 h-4" />
              </button>
              <button 
                @click="scrollProjects('next')" 
                class="w-8 h-8 rounded-full border border-zinc-800 bg-[#121216] hover:border-[#d92332] hover:text-white text-zinc-400 flex items-center justify-center transition-colors cursor-pointer shadow-sm"
                title="Scroll Selanjutnya"
                aria-label="Next Projects"
              >
                <ChevronRight class="w-4 h-4" />
              </button>
            </div>
          </div>
        </div>

        <!-- HORIZONTAL SCROLL CAROUSEL CONTAINER (Single Row - No Stacking!) -->
        <div 
          ref="scrollContainer"
          class="flex flex-nowrap gap-6 sm:gap-8 overflow-x-auto scroll-smooth snap-x snap-mandatory pb-5 pt-2 project-scroll select-none cursor-grab"
        >
          <div 
            v-for="(project, pIdx) in filteredProjects" 
            :key="project.id"
            @click="openProjectModal(project)"
            class="shrink-0 w-[85vw] sm:w-[350px] md:w-[380px] lg:w-[400px] snap-start group flex flex-col cursor-pointer transition-all duration-300"
          >
            <!-- Project Mockup Frame (Sleek Wireframe tailored to each project) -->
            <div class="relative w-full aspect-[16/10] bg-[#111115] border border-zinc-800 rounded-xs overflow-hidden flex flex-col justify-between p-5 transition-all duration-300 group-hover:border-[#d92332]/60 group-hover:shadow-[0_10px_30px_rgba(217,35,50,0.15)]">
              <!-- Top Mockup Bar -->
              <div class="flex items-center justify-between text-[10px] font-mono text-zinc-500 uppercase pb-2 border-b border-zinc-800/70">
                <span class="tracking-widest text-[#d92332] font-bold">{{ project.title }}</span>
                <span class="text-[9px] text-zinc-500">{{ project.badge || 'CASE STUDY' }}</span>
              </div>

              <!-- Center Graphic Dummy Wireframe Content -->
              <div class="my-auto py-2 space-y-1.5">
                <div class="text-xs sm:text-sm font-bold text-white uppercase tracking-wider line-clamp-1">
                  {{ project.subtitle }}
                </div>
                <p class="text-[10px] text-zinc-400 line-clamp-2 leading-relaxed">
                  {{ project.description }}
                </p>
                <div class="flex flex-wrap gap-1 pt-1">
                  <span 
                    v-for="(tag, tIdx) in project.tags.slice(0, 3)" 
                    :key="tIdx"
                    class="px-1.5 py-0.5 rounded-xs bg-zinc-900 border border-zinc-800 text-[9px] font-mono text-zinc-400"
                  >
                    {{ tag }}
                  </span>
                </div>
              </div>

              <!-- Bottom Mockup Indicator -->
              <div class="flex items-center justify-between text-[9px] text-zinc-500 font-mono pt-2 border-t border-zinc-900">
                <span>VIEW CASE STUDY</span>
                <span>{{ project.categoryName }}</span>
              </div>
            </div>

            <!-- Card Bottom Info (Reference Layout: 01, 02, etc. + Title + Arrow) -->
            <div class="flex items-center justify-between mt-4">
              <div class="flex items-baseline gap-3">
                <span class="font-display font-bold text-2xl sm:text-3xl text-[#d92332] leading-none">
                  0{{ pIdx + 1 }}
                </span>
                <div class="flex flex-col">
                  <span class="text-xs sm:text-sm font-bold tracking-wider text-white uppercase group-hover:text-[#d92332] transition-colors">
                    {{ project.title }}
                  </span>
                  <span class="text-[10px] sm:text-[11px] font-semibold tracking-wider text-zinc-400 uppercase">
                    {{ project.categoryName }}
                  </span>
                </div>
              </div>
              <ArrowRight class="w-4 h-4 text-zinc-600 group-hover:text-white group-hover:translate-x-1 transition-all" />
            </div>
          </div>
        </div>

        <!-- Horizontal Scroll Navigation Hint / Mobile Arrows -->
        <div class="flex items-center justify-between pt-3 text-[10px] font-mono text-zinc-500 select-none">
          <div class="flex items-center gap-2">
            <span class="w-2 h-2 rounded-full bg-[#d92332] animate-pulse"></span>
            <span>GESER / SCROLL HORIZONTAL UNTUK MELIHAT 7 PROYEK</span>
          </div>
          <!-- Mobile Prev/Next -->
          <div class="flex sm:hidden items-center gap-2">
            <button 
              @click="scrollProjects('prev')" 
              class="w-7 h-7 rounded-full border border-zinc-800 bg-[#121216] text-zinc-400 flex items-center justify-center cursor-pointer"
            >
              <ChevronLeft class="w-3.5 h-3.5" />
            </button>
            <button 
              @click="scrollProjects('next')" 
              class="w-7 h-7 rounded-full border border-zinc-800 bg-[#121216] text-zinc-400 flex items-center justify-center cursor-pointer"
            >
              <ChevronRight class="w-3.5 h-3.5" />
            </button>
          </div>
        </div>
      </section>

      <!-- SECTION 3: 3-COLUMN BENTO (EDUCATION & SKILLS | WORK PROCESS | PHILOSOPHY BANNER) -->
      <section id="about" class="py-12 sm:py-16 border-t border-zinc-900/90 scroll-mt-20">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-12 gap-8 items-stretch">
          
          <!-- COLUMN 1: EDUCATION & SKILLS (4 Cols) -->
          <div class="md:col-span-1 lg:col-span-4 flex flex-col justify-between space-y-8 pr-0 lg:pr-4">
            <div>
              <h3 class="text-sm sm:text-base font-bold tracking-[0.2em] text-white uppercase pb-3 border-b border-zinc-800">
                EDUCATION & SKILLS
              </h3>

              <!-- Education Sub-Header -->
              <div class="pt-6">
                <div class="text-[11px] font-bold text-[#d92332] tracking-[0.22em] uppercase mb-4">
                  EDUCATION
                </div>

                <div class="space-y-4">
                  <!-- Education 1: S1 Sistem Informasi UPNVJT -->
                  <div class="flex justify-between items-start gap-2">
                    <div>
                      <h4 class="text-xs sm:text-[13px] font-bold text-zinc-100">
                        S1 Sistem Informasi
                      </h4>
                      <p class="text-[11px] text-zinc-400">
                        UPN "Veteran" Jawa Timur
                      </p>
                      <p class="text-[10px] text-zinc-500 mt-1 leading-relaxed">
                        Fokus pada analisis kebutuhan sistem, manajemen TI, dan UI/UX berbasis riset.
                      </p>
                    </div>
                    <span class="text-[11px] font-mono text-zinc-500 whitespace-nowrap">
                      2022 - Present
                    </span>
                  </div>

                  <!-- Education 2: UI/UX Certification -->
                  <div class="flex justify-between items-start gap-2 pt-2 border-t border-zinc-900">
                    <div>
                      <h4 class="text-xs sm:text-[13px] font-bold text-zinc-100">
                        UI/UX Design Certification
                      </h4>
                      <p class="text-[11px] text-zinc-400">
                        Google Career Certificates / ISCOM
                      </p>
                    </div>
                    <span class="text-[11px] font-mono text-zinc-500 whitespace-nowrap">
                      2023 - 2024
                    </span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Skills Matrix (Clean outlined pills, no emojis) -->
            <div class="pt-6 border-t border-zinc-900">
              <div class="text-[11px] font-bold text-[#d92332] tracking-[0.22em] uppercase mb-4">
                SKILLS & TOOLS
              </div>

              <div class="flex flex-wrap gap-2">
                <span 
                  v-for="(skill, sIdx) in skillsList" 
                  :key="sIdx"
                  class="px-2.5 py-1.5 rounded-xs bg-[#111115] border border-zinc-800 text-[10px] sm:text-[11px] font-medium tracking-wider text-zinc-300 uppercase hover:border-[#d92332] hover:text-white transition-colors"
                >
                  {{ skill }}
                </span>
              </div>
            </div>
          </div>

          <!-- COLUMN 2: WORK PROCESS (4 Cols) -->
          <div id="process" class="md:col-span-1 lg:col-span-4 flex flex-col space-y-6 lg:border-l lg:border-zinc-900/90 lg:pl-8 scroll-mt-20">
            <h3 class="text-sm sm:text-base font-bold tracking-[0.2em] text-white uppercase pb-3 border-b border-zinc-800">
              WORK PROCESS
            </h3>

            <!-- 5-Step Process Timeline with Lucide SVG Icons -->
            <div class="relative pt-2 space-y-6">
              <!-- Connecting Line -->
              <div class="absolute left-[39px] top-6 bottom-6 w-px bg-zinc-800/80 -z-0"></div>

              <!-- Step 1: DISCOVER -->
              <div class="relative flex items-start gap-3.5 group">
                <span class="text-[11px] font-mono font-bold text-[#d92332] pt-1.5 w-4 text-right">01</span>
                <div class="w-8 h-8 rounded-full bg-[#141419] border border-zinc-800 flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-[#d92332] transition-colors shrink-0 z-10 shadow-xs">
                  <Search class="w-3.5 h-3.5" />
                </div>
                <div class="flex-1 pt-0.5">
                  <h4 class="text-xs font-bold text-[#d92332] tracking-wider uppercase">DISCOVER</h4>
                  <p class="text-[11px] text-zinc-400 leading-relaxed mt-0.5">Understanding goals, audience, and project requirements.</p>
                </div>
              </div>

              <!-- Step 2: IDEATE -->
              <div class="relative flex items-start gap-3.5 group">
                <span class="text-[11px] font-mono font-bold text-[#d92332] pt-1.5 w-4 text-right">02</span>
                <div class="w-8 h-8 rounded-full bg-[#141419] border border-zinc-800 flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-[#d92332] transition-colors shrink-0 z-10 shadow-xs">
                  <Lightbulb class="w-3.5 h-3.5" />
                </div>
                <div class="flex-1 pt-0.5">
                  <h4 class="text-xs font-bold text-[#d92332] tracking-wider uppercase">IDEATE</h4>
                  <p class="text-[11px] text-zinc-400 leading-relaxed mt-0.5">Planning, wireframing, and creating the right concept.</p>
                </div>
              </div>

              <!-- Step 3: DESIGN -->
              <div class="relative flex items-start gap-3.5 group">
                <span class="text-[11px] font-mono font-bold text-[#d92332] pt-1.5 w-4 text-right">03</span>
                <div class="w-8 h-8 rounded-full bg-[#141419] border border-zinc-800 flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-[#d92332] transition-colors shrink-0 z-10 shadow-xs">
                  <PenTool class="w-3.5 h-3.5" />
                </div>
                <div class="flex-1 pt-0.5">
                  <h4 class="text-xs font-bold text-[#d92332] tracking-wider uppercase">DESIGN</h4>
                  <p class="text-[11px] text-zinc-400 leading-relaxed mt-0.5">Crafting visual design with a focus on user experience.</p>
                </div>
              </div>

              <!-- Step 4: DEVELOP -->
              <div class="relative flex items-start gap-3.5 group">
                <span class="text-[11px] font-mono font-bold text-[#d92332] pt-1.5 w-4 text-right">04</span>
                <div class="w-8 h-8 rounded-full bg-[#141419] border border-zinc-800 flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-[#d92332] transition-colors shrink-0 z-10 shadow-xs">
                  <Code class="w-3.5 h-3.5" />
                </div>
                <div class="flex-1 pt-0.5">
                  <h4 class="text-xs font-bold text-[#d92332] tracking-wider uppercase">DEVELOP</h4>
                  <p class="text-[11px] text-zinc-400 leading-relaxed mt-0.5">Building fast, responsive, and high-performing websites.</p>
                </div>
              </div>

              <!-- Step 5: DELIVER -->
              <div class="relative flex items-start gap-3.5 group">
                <span class="text-[11px] font-mono font-bold text-[#d92332] pt-1.5 w-4 text-right">05</span>
                <div class="w-8 h-8 rounded-full bg-[#141419] border border-zinc-800 flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-[#d92332] transition-colors shrink-0 z-10 shadow-xs">
                  <Send class="w-3.5 h-3.5" />
                </div>
                <div class="flex-1 pt-0.5">
                  <h4 class="text-xs font-bold text-[#d92332] tracking-wider uppercase">DELIVER</h4>
                  <p class="text-[11px] text-zinc-400 leading-relaxed mt-0.5">Testing, optimizing, and launching with perfection.</p>
                </div>
              </div>

            </div>
          </div>

          <!-- COLUMN 3: SOLID CRIMSON RED PHILOSOPHY CARD (4 Cols) -->
          <div class="md:col-span-2 lg:col-span-4 bg-[#7a0c14] border border-[#94111d] rounded-xs p-8 sm:p-10 flex flex-col justify-between shadow-2xl relative overflow-hidden select-none min-h-[400px]">
            <!-- Quote Mark -->
            <div class="font-serif text-6xl text-white/20 leading-none select-none">
              “
            </div>

            <!-- Quote Text -->
            <div class="space-y-4 my-auto">
              <blockquote class="text-lg sm:text-xl font-medium text-white leading-snug">
                Good design is not just how it looks, but how it works.
              </blockquote>

              <!-- Signature -->
              <div class="font-script text-3xl sm:text-4xl text-white/90 pt-3">
                Septian
              </div>
            </div>

            <!-- Card Bottom Message -->
            <div class="pt-6 border-t border-white/10 flex items-center justify-between">
              <div class="text-[11px] font-bold tracking-[0.2em] text-white/90 uppercase leading-relaxed">
                LET'S CREATE<br/>SOMETHING GREAT<br/>TOGETHER.
              </div>
              <Sparkle class="w-4 h-4 text-white/90 fill-current" />
            </div>

          </div>

        </div>
      </section>

      <!-- SECTION 4: PROFESSIONAL & ORGANIZATIONAL EXPERIENCE (HORIZONTAL SCROLL) -->
      <section id="experience" class="py-12 sm:py-16 border-t border-zinc-900/90 scroll-mt-20">
        <div class="flex items-end justify-between gap-4 mb-6 sm:mb-8">
          <div>
            <span class="text-[10px] font-bold text-[#d92332] tracking-[0.26em] uppercase">CAREER JOURNEY</span>
            <h2 class="text-base sm:text-xl font-bold tracking-[0.2em] text-white uppercase mt-0.5">
              EXPERIENCE & LEADERSHIP
            </h2>
          </div>

          <!-- Carousel Prev & Next Arrows (Desktop) -->
          <div class="hidden sm:flex items-center gap-2 pl-2 border-l border-zinc-800">
            <button 
              @click="scrollExperience('prev')" 
              class="w-8 h-8 rounded-full border border-zinc-800 bg-[#121216] hover:border-[#d92332] hover:text-white text-zinc-400 flex items-center justify-center transition-colors cursor-pointer shadow-sm"
              title="Scroll Sebelumnya"
              aria-label="Previous Experience"
            >
              <ChevronLeft class="w-4 h-4" />
            </button>
            <button 
              @click="scrollExperience('next')" 
              class="w-8 h-8 rounded-full border border-zinc-800 bg-[#121216] hover:border-[#d92332] hover:text-white text-zinc-400 flex items-center justify-center transition-colors cursor-pointer shadow-sm"
              title="Scroll Selanjutnya"
              aria-label="Next Experience"
            >
              <ChevronRight class="w-4 h-4" />
            </button>
          </div>
        </div>

        <!-- Horizontal Scroll Container -->
        <div 
          ref="expScrollContainer"
          class="flex flex-nowrap gap-6 overflow-x-auto scroll-smooth snap-x snap-mandatory pb-5 pt-2 project-scroll select-none cursor-grab"
        >
          <div 
            v-for="(exp, eIdx) in experiences" 
            :key="eIdx"
            :class="[
              'shrink-0 w-[85vw] sm:w-[380px] md:w-[420px] snap-start bg-[#111115] border p-6 rounded-xs transition-all space-y-3.5 flex flex-col justify-between shadow-sm',
              exp.featured ? 'border-[#d92332]/60 shadow-[0_4px_25px_rgba(217,35,50,0.15)]' : 'border-zinc-800/80 hover:border-[#d92332]/50'
            ]"
          >
            <div class="space-y-3">
              <div class="flex flex-wrap justify-between items-start gap-2">
                <div>
                  <div class="flex items-center gap-2">
                    <h3 class="text-sm sm:text-base font-bold text-white uppercase tracking-wide">{{ exp.role }}</h3>
                    <span v-if="exp.featured" class="px-2 py-0.5 rounded-xs bg-[#d92332]/20 border border-[#d92332]/50 text-[9px] font-mono text-[#d92332] uppercase tracking-wider font-semibold">
                      RECOMMENDED
                    </span>
                  </div>
                  <div class="text-xs font-semibold text-[#d92332] mt-0.5">{{ exp.company }}</div>
                </div>
                <span class="px-2 py-0.5 rounded-xs bg-[#18181f] border border-zinc-800 text-[10px] font-mono text-zinc-400 whitespace-nowrap">
                  {{ exp.period }}
                </span>
              </div>

              <!-- Bullet points if available -->
              <ul v-if="exp.points && exp.points.length" class="space-y-1.5 text-xs text-zinc-300 list-none pl-0">
                <li v-for="(pt, pIdx) in exp.points" :key="pIdx" class="flex items-start gap-2">
                  <span class="text-[#d92332] font-bold leading-none mt-1">✦</span>
                  <span class="leading-relaxed">{{ pt }}</span>
                </li>
              </ul>

              <!-- Paragraph description fallback -->
              <p v-else-if="exp.description" class="text-xs text-zinc-400 leading-relaxed">
                {{ exp.description }}
              </p>
            </div>

            <div class="flex flex-wrap gap-1.5 pt-2 border-t border-zinc-900">
              <span 
                v-for="(tag, tIdx) in exp.tags" 
                :key="tIdx"
                class="px-2 py-0.5 bg-zinc-900 border border-zinc-800 text-[9px] font-mono text-zinc-400 rounded-xs"
              >
                {{ tag }}
              </span>
            </div>
          </div>
        </div>

        <!-- Horizontal Scroll Navigation Hint / Mobile Arrows -->
        <div class="flex items-center justify-between pt-3 text-[10px] font-mono text-zinc-500 select-none">
          <div class="flex items-center gap-2">
            <span class="w-2 h-2 rounded-full bg-[#d92332] animate-pulse"></span>
            <span>GESER / SCROLL HORIZONTAL UNTUK MELIHAT 5 PENGALAMAN</span>
          </div>
          <!-- Mobile Prev/Next -->
          <div class="flex sm:hidden items-center gap-2">
            <button 
              @click="scrollExperience('prev')" 
              class="w-7 h-7 rounded-full border border-zinc-800 bg-[#121216] text-zinc-400 flex items-center justify-center cursor-pointer"
            >
              <ChevronLeft class="w-3.5 h-3.5" />
            </button>
            <button 
              @click="scrollExperience('next')" 
              class="w-7 h-7 rounded-full border border-zinc-800 bg-[#121216] text-zinc-400 flex items-center justify-center cursor-pointer"
            >
              <ChevronRight class="w-3.5 h-3.5" />
            </button>
          </div>
        </div>
      </section>

      <!-- SECTION 5: NATIONAL & INTERNATIONAL AWARDS (HORIZONTAL SCROLL) -->
      <section id="achievements" class="py-12 sm:py-16 border-t border-zinc-900/90 scroll-mt-20">
        <div class="flex items-end justify-between gap-4 mb-6 sm:mb-8">
          <div>
            <span class="text-[10px] font-bold text-[#d92332] tracking-[0.26em] uppercase">PROVEN EXCELLENCE</span>
            <h2 class="text-base sm:text-xl font-bold tracking-[0.2em] text-white uppercase mt-0.5">
              HONORS & COMPETITIONS
            </h2>
          </div>

          <!-- Carousel Prev & Next Arrows (Desktop) -->
          <div class="hidden sm:flex items-center gap-2 pl-2 border-l border-zinc-800">
            <button 
              @click="scrollAchievements('prev')" 
              class="w-8 h-8 rounded-full border border-zinc-800 bg-[#121216] hover:border-[#d92332] hover:text-white text-zinc-400 flex items-center justify-center transition-colors cursor-pointer shadow-sm"
              title="Scroll Sebelumnya"
              aria-label="Previous Achievement"
            >
              <ChevronLeft class="w-4 h-4" />
            </button>
            <button 
              @click="scrollAchievements('next')" 
              class="w-8 h-8 rounded-full border border-zinc-800 bg-[#121216] hover:border-[#d92332] hover:text-white text-zinc-400 flex items-center justify-center transition-colors cursor-pointer shadow-sm"
              title="Scroll Selanjutnya"
              aria-label="Next Achievement"
            >
              <ChevronRight class="w-4 h-4" />
            </button>
          </div>
        </div>

        <!-- Horizontal Scroll Container -->
        <div 
          ref="achieveScrollContainer"
          class="flex flex-nowrap gap-6 overflow-x-auto scroll-smooth snap-x snap-mandatory pb-5 pt-2 project-scroll select-none cursor-grab"
        >
          <div 
            v-for="(achieve, aIdx) in achievements" 
            :key="aIdx"
            class="shrink-0 w-[85vw] sm:w-[320px] md:w-[360px] snap-start bg-[#111115] border border-zinc-800 hover:border-[#d92332]/60 p-6 rounded-xs transition-all flex flex-col justify-between space-y-4 shadow-sm"
          >
            <div class="space-y-2.5">
              <div class="flex items-center justify-between">
                <span class="font-display font-bold text-2xl text-[#d92332]">0{{ aIdx + 1 }}</span>
                <span class="px-2 py-0.5 rounded-xs bg-zinc-900 border border-zinc-800 text-[10px] font-mono text-[#d92332]">
                  {{ achieve.year }}
                </span>
              </div>
              <h3 class="text-sm sm:text-base font-bold text-white uppercase tracking-wide">
                {{ achieve.title }}
              </h3>
              <div class="text-[11px] font-mono text-zinc-400 uppercase tracking-wider">
                {{ achieve.event }}
              </div>
              <p class="text-xs text-zinc-400 leading-relaxed">
                {{ achieve.description }}
              </p>
            </div>

            <div class="pt-3 border-t border-zinc-900 flex items-center gap-2 text-[10px] font-mono text-[#d92332] uppercase">
              <span class="w-1.5 h-1.5 rounded-full bg-[#d92332]"></span>
              <span>VERIFIED COMPETITION AWARD</span>
            </div>
          </div>
        </div>

        <!-- Horizontal Scroll Navigation Hint / Mobile Arrows -->
        <div class="flex items-center justify-between pt-3 text-[10px] font-mono text-zinc-500 select-none">
          <div class="flex items-center gap-2">
            <span class="w-2 h-2 rounded-full bg-[#d92332] animate-pulse"></span>
            <span>GESER / SCROLL HORIZONTAL UNTUK MELIHAT 5 PRESTASI</span>
          </div>
          <!-- Mobile Prev/Next -->
          <div class="flex sm:hidden items-center gap-2">
            <button 
              @click="scrollAchievements('prev')" 
              class="w-7 h-7 rounded-full border border-zinc-800 bg-[#121216] text-zinc-400 flex items-center justify-center cursor-pointer"
            >
              <ChevronLeft class="w-3.5 h-3.5" />
            </button>
            <button 
              @click="scrollAchievements('next')" 
              class="w-7 h-7 rounded-full border border-zinc-800 bg-[#121216] text-zinc-400 flex items-center justify-center cursor-pointer"
            >
              <ChevronRight class="w-3.5 h-3.5" />
            </button>
          </div>
        </div>
      </section>

      <!-- SECTION 6: LET'S WORK TOGETHER (CONTACT & WORKSPACE MOCKUP) -->
      <section id="contact" class="py-12 sm:py-16 border-t border-zinc-900/90 scroll-mt-20">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
          
          <!-- LEFT / CONTACT INFO (7 Cols) -->
          <div class="lg:col-span-7 space-y-6">
            <div>
              <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold tracking-tight text-white uppercase flex items-center gap-3">
                <span>LET'S WORK</span>
              </h2>
              <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold tracking-tight text-white uppercase flex items-center gap-3">
                <span>TOGETHER</span>
                <Sparkle class="w-5 h-5 text-[#d92332] fill-current" />
              </h2>
            </div>

            <p class="text-xs sm:text-sm text-zinc-300 font-normal leading-relaxed max-w-md">
              Saya selalu terbuka untuk tawaran pekerjaan full-time, magang (internship), freelance UI/UX & Web Development, atau kolaborasi inovatif lainnya.
            </p>

            <!-- 4 Contact Points with Circular Outline Icons -->
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-2">
              
              <!-- Email -->
              <a href="mailto:listiaseptian11@gmail.com" class="flex items-center gap-3 group">
                <div class="w-8 h-8 rounded-full border border-zinc-800 bg-[#141419] flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-white transition-colors shrink-0">
                  <Mail class="w-3.5 h-3.5" />
                </div>
                <span class="text-xs text-zinc-300 group-hover:text-white transition-colors">
                  listiaseptian11@gmail.com
                </span>
              </a>

              <!-- Portfolio / GitHub -->
              <a href="https://github.com/Septian-Wq11" target="_blank" class="flex items-center gap-3 group">
                <div class="w-8 h-8 rounded-full border border-zinc-800 bg-[#141419] flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-white transition-colors shrink-0">
                  <Globe class="w-3.5 h-3.5" />
                </div>
                <span class="text-xs text-zinc-300 group-hover:text-white transition-colors">
                  github.com/Septian-Wq11
                </span>
              </a>

              <!-- WhatsApp / Phone -->
              <a href="https://wa.me/6281234567890" target="_blank" class="flex items-center gap-3 group">
                <div class="w-8 h-8 rounded-full border border-zinc-800 bg-[#141419] flex items-center justify-center text-zinc-400 group-hover:border-[#d92332] group-hover:text-white transition-colors shrink-0">
                  <Phone class="w-3.5 h-3.5" />
                </div>
                <span class="text-xs text-zinc-300 group-hover:text-white transition-colors">
                  +62 812 3456 7890
                </span>
              </a>

              <!-- Location -->
              <div class="flex items-center gap-3 select-none">
                <div class="w-8 h-8 rounded-full border border-zinc-800 bg-[#141419] flex items-center justify-center text-zinc-400 shrink-0">
                  <MapPin class="w-3.5 h-3.5" />
                </div>
                <span class="text-xs text-zinc-300">
                  Surabaya, Jawa Timur, Indonesia
                </span>
              </div>

            </div>

            <!-- CTA Buttons -->
            <div class="pt-2 flex flex-wrap gap-3">
              <a 
                href="https://mail.google.com/mail/?view=cm&fs=1&to=listiaseptian11@gmail.com" 
                target="_blank"
                class="inline-flex items-center gap-3 px-5 py-2.5 rounded-full border border-[#d92332]/50 bg-[#7a0c14]/30 hover:bg-[#7a0c14]/70 text-white text-[11px] font-bold tracking-[0.2em] uppercase transition-all duration-300 shadow-md hover:shadow-[#d92332]/20"
              >
                <div class="w-5 h-5 rounded-full bg-[#d92332] flex items-center justify-center text-white">
                  <ArrowRight class="w-3 h-3" />
                </div>
                <span>SEND DIRECT EMAIL</span>
              </a>

              <a 
                href="mailto:listiaseptian11@gmail.com" 
                class="inline-flex items-center gap-2 px-4 py-2.5 rounded-full border border-zinc-800 bg-zinc-900/60 hover:bg-zinc-800 text-zinc-300 text-[11px] font-mono tracking-wider uppercase transition-colors"
              >
                <span>OPEN CLIENT MAIL</span>
              </a>
            </div>
          </div>

          <!-- RIGHT / SLEEK DUMMY LAPTOP & DESK WORKSPACE MOCKUP (5 Cols) -->
          <div class="lg:col-span-5 flex justify-center lg:justify-end select-none">
            <div class="relative w-full max-w-[380px] aspect-[4/3] flex items-center justify-center">
              
              <svg viewBox="0 0 380 280" class="w-full h-full drop-shadow-2xl" fill="none" xmlns="http://www.w3.org/2000/svg">
                <!-- Desk Surface Shadow -->
                <ellipse cx="190" cy="245" rx="150" ry="20" fill="#000000" opacity="0.8" />

                <!-- Coffee Mug with Monogram 'S' -->
                <ellipse cx="70" cy="235" rx="16" ry="6" fill="#000000" opacity="0.6" />
                <rect x="56" y="200" width="28" height="34" rx="3" fill="#141418" stroke="#272730" stroke-width="1.5" />
                <ellipse cx="70" cy="200" rx="14" ry="4" fill="#09090b" stroke="#272730" stroke-width="1.5" />
                <path d="M84 208 C90 208 92 222 84 224" stroke="#272730" stroke-width="2" fill="none" />
                <text x="70" y="222" font-family="'Plus Jakarta Sans', sans-serif" font-size="10" font-weight="bold" fill="#71717a" text-anchor="middle">S</text>

                <!-- Laptop Screen Chassis -->
                <path d="M100 70 L280 70 L300 210 L120 210 Z" fill="#0d0d10" stroke="#2b2b35" stroke-width="2" />
                
                <!-- Screen Glass -->
                <path d="M107 77 L273 77 L293 203 L127 203 Z" fill="#09090b" />
                
                <!-- Display Graphic Content -->
                <rect x="125" y="85" width="40" height="4" rx="1" fill="#71717a" />
                <text x="135" y="115" font-family="'Plus Jakarta Sans', sans-serif" font-size="9" font-weight="800" fill="#ffffff" letter-spacing="0.5">WE</text>
                <text x="135" y="126" font-family="'Plus Jakarta Sans', sans-serif" font-size="9" font-weight="800" fill="#ffffff" letter-spacing="0.5">DESIGN</text>
                <text x="135" y="137" font-family="'Plus Jakarta Sans', sans-serif" font-size="9" font-weight="800" fill="#d92332" letter-spacing="0.5">DIGITAL</text>
                <text x="135" y="148" font-family="'Plus Jakarta Sans', sans-serif" font-size="8" font-weight="700" fill="#a1a1aa" letter-spacing="0.5">EXPERIENCES</text>

                <!-- Crimson Aesthetic Bar -->
                <path d="M210 115 L245 115 L235 140 L200 140 Z" fill="#b31925" />
                <path d="M248 115 L260 115 L250 140 L238 140 Z" fill="#ffffff" opacity="0.8" />
                
                <!-- Keyboard Base Deck -->
                <path d="M120 210 L300 210 L320 240 L100 240 Z" fill="#18181e" stroke="#2b2b35" stroke-width="1.5" />
                <path d="M185 224 L235 224 L238 236 L182 236 Z" fill="#111116" stroke="#22222a" stroke-width="1" />
                <line x1="99" y1="240" x2="321" y2="240" stroke="#3f3f4e" stroke-width="1.5" />
              </svg>

            </div>
          </div>

        </div>
      </section>

      <!-- FOOTER -->
      <footer class="pt-8 pb-4 border-t border-zinc-900/90 select-none flex flex-col sm:flex-row items-center justify-between text-[11px] font-mono text-zinc-500 gap-2">
        <div>
          © 2026 SEPTIAN LISTIA TRI CAHYO. ALL RIGHTS RESERVED.
        </div>
        <div class="text-[#d92332] font-semibold tracking-wider">
          EDITORIAL REDESIGN • V2.0
        </div>
      </footer>

    </div>

    <!-- PROJECT DETAIL MODAL (CLEAN & MINIMALIST) -->
    <div 
      v-if="activeModalProject" 
      class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md transition-all"
      @click.self="activeModalProject = null"
    >
      <div class="bg-[#121216] border border-zinc-800 max-w-xl w-full p-6 sm:p-8 rounded-xs shadow-2xl relative space-y-5">
        
        <!-- Header -->
        <div class="flex items-center justify-between pb-4 border-b border-zinc-800">
          <div>
            <span class="text-[10px] font-mono text-[#d92332] uppercase tracking-wider">{{ activeModalProject.categoryName }}</span>
            <h3 class="text-xl sm:text-2xl font-bold text-white uppercase">{{ activeModalProject.title }}</h3>
            <p class="text-xs text-zinc-400 mt-0.5">{{ activeModalProject.subtitle }}</p>
          </div>
          <button 
            @click="activeModalProject = null" 
            class="w-8 h-8 rounded-full border border-zinc-800 text-zinc-400 hover:text-white hover:border-[#d92332] flex items-center justify-center transition-colors cursor-pointer"
          >
            ✕
          </button>
        </div>

        <!-- Body -->
        <p class="text-xs sm:text-sm text-zinc-300 leading-relaxed">
          {{ activeModalProject.description }}
        </p>

        <!-- Tags -->
        <div class="space-y-2 pt-2">
          <div class="text-[10px] font-mono uppercase tracking-wider text-zinc-500">Methodology & Technologies</div>
          <div class="flex flex-wrap gap-1.5">
            <span 
              v-for="(tag, tIdx) in activeModalProject.tags" 
              :key="tIdx"
              class="px-2.5 py-1 bg-zinc-900 border border-zinc-800 text-zinc-300 text-[10px] font-mono rounded-xs"
            >
              {{ tag }}
            </span>
          </div>
        </div>

        <!-- Footer -->
        <div class="pt-4 border-t border-zinc-800/80 flex items-center justify-between">
          <span class="text-[10px] font-mono text-zinc-500">[ Ready for user screenshot assets ]</span>
          <button 
            @click="activeModalProject = null" 
            class="px-4 py-2 bg-[#d92332] hover:bg-[#b31925] text-white text-xs font-bold uppercase tracking-wider transition-colors cursor-pointer rounded-xs"
          >
            Close
          </button>
        </div>
      </div>
    </div>

  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import { 
  Sparkle, 
  ArrowRight, 
  ChevronLeft,
  ChevronRight,
  Search, 
  Lightbulb, 
  PenTool, 
  Code, 
  Send, 
  Mail, 
  Globe, 
  Phone, 
  MapPin 
} from 'lucide-vue-next';

import profileImg from '/public/FotoProfile.png?url';

// Mobile menu toggle state
const mobileMenuOpen = ref(false);

// Reference to horizontal scroll containers
const scrollContainer = ref(null);
const expScrollContainer = ref(null);
const achieveScrollContainer = ref(null);

const scrollProjects = (direction) => {
  if (!scrollContainer.value) return;
  const cardWidth = scrollContainer.value.querySelector('.shrink-0')?.offsetWidth || 380;
  const gap = 24;
  const scrollAmount = (cardWidth + gap) * (direction === 'next' ? 1 : -1);
  scrollContainer.value.scrollBy({ left: scrollAmount, behavior: 'smooth' });
};

const scrollExperience = (direction) => {
  if (!expScrollContainer.value) return;
  const cardWidth = expScrollContainer.value.querySelector('.shrink-0')?.offsetWidth || 400;
  const gap = 24;
  const scrollAmount = (cardWidth + gap) * (direction === 'next' ? 1 : -1);
  expScrollContainer.value.scrollBy({ left: scrollAmount, behavior: 'smooth' });
};

const scrollAchievements = (direction) => {
  if (!achieveScrollContainer.value) return;
  const cardWidth = achieveScrollContainer.value.querySelector('.shrink-0')?.offsetWidth || 340;
  const gap = 24;
  const scrollAmount = (cardWidth + gap) * (direction === 'next' ? 1 : -1);
  achieveScrollContainer.value.scrollBy({ left: scrollAmount, behavior: 'smooth' });
};

// Category filter
const activeCategory = ref('all');

const projectCategories = [
  { id: 'all', label: 'All Works' },
  { id: 'uiux', label: 'UI/UX Design' },
  { id: 'web', label: 'Web Dev' },
  { id: 'mobile', label: 'Mobile App' }
];

const setCategory = (catId) => {
  activeCategory.value = catId;
  if (scrollContainer.value) {
    scrollContainer.value.scrollTo({ left: 0, behavior: 'smooth' });
  }
};

// Active project for modal preview
const activeModalProject = ref(null);

const openProjectModal = (proj) => {
  activeModalProject.value = proj;
};

// All Original Skills
const skillsList = [
  'FIGMA',
  'VUE.JS',
  'TAILWIND CSS',
  'JAVASCRIPT',
  'HTML5',
  'CSS3',
  'PHP',
  'MYSQL',
  'FLUTTER',
  'JAVA',
  'DESIGN THINKING',
  'SYSTEM ANALYSIS',
  'USABILITY TESTING',
  'WIREFRAMING'
];

// All Original Projects
const projects = [
  {
    id: 1,
    title: 'PILAH',
    subtitle: 'Platform Integrasi Limbah Konveksi untuk Akselerasi Hasil Usaha',
    category: 'uiux',
    categoryName: 'UI/UX CASE STUDY',
    badge: 'JUARA 1 UI/UX',
    description: 'PILAH merupakan konsep aplikasi mobile yang dirancang untuk menghubungkan konveksi sebagai penghasil limbah tekstil dengan UMKM upcycling sebagai pengguna bahan baku. Aplikasi ini membantu pengguna menemukan material limbah, memahami kondisi dan informasi material, melakukan transaksi, serta membangun kemitraan untuk memperoleh pasokan yang lebih berkelanjutan.',
    tags: ['Design Thinking', 'User Research', 'Mobile App', 'E-Commerce', 'Usability Testing']
  },
  {
    id: 2,
    title: 'SIPOSYA',
    subtitle: 'Digital Posyandu Mobile Application',
    category: 'uiux',
    categoryName: 'HEALTHCARE MOBILE APP',
    badge: 'HEALTHCARE',
    description: 'Perancangan UI/UX aplikasi layanan Posyandu berbasis mobile untuk mendigitalkan pencatatan tumbuh kembang balita dan layanan kesehatan masyarakat terpadu.',
    tags: ['Figma', 'UI/UX', 'Mobile App', 'Design System', 'User Research']
  },
  {
    id: 3,
    title: 'SIROW',
    subtitle: 'Smart Farming IoT & Water Monitoring',
    category: 'uiux',
    categoryName: 'SMART AGRICULTURE IOT',
    badge: 'IOT CONCEPT',
    description: 'Perancangan UI/UX aplikasi smart farming berbasis mobile terintegrasi IoT untuk memonitor debit air, kualitas irigasi, dan otomasi penyiraman pertanian.',
    tags: ['Figma', 'UI/UX', 'Mobile App', 'IoT Concept', 'Design System']
  },
  {
    id: 4,
    title: 'FLOMART',
    subtitle: 'Plant & Flora Digital Marketplace',
    category: 'uiux',
    categoryName: 'E-COMMERCE MARKETPLACE',
    badge: 'E-COMMERCE',
    description: 'Desain marketplace tanaman hias dengan navigasi pencarian visual berdasarkan jenis perawatan, pencahayaan, dan kemudahan transaksi.',
    tags: ['Figma', 'E-Commerce', 'User Flow', 'Wireframing']
  },
  {
    id: 5,
    title: 'LOUSEL',
    subtitle: 'Mental Health & Emotional Assistant',
    category: 'uiux',
    categoryName: 'HEALTHTECH MOBILE APP',
    badge: 'HEALTHTECH',
    description: 'Aplikasi pendamping kesehatan mental yang dilengkapi fitur mood tracking harian, relaksasi terbimbing, dan jurnal emosi.',
    tags: ['UI/UX', 'Design Thinking', 'Mobile Prototype', 'HealthTech']
  },
  {
    id: 6,
    title: 'Marketplace Tanaman',
    subtitle: 'Full-Stack E-Commerce Web System',
    category: 'web',
    categoryName: 'FULL-STACK WEB DEV',
    badge: 'WEB SYSTEM',
    description: 'Pengembangan website jual-beli tanaman lengkap dengan katalog dinamis, manajemen inventaris produk, dan sistem transaksi terintegrasi.',
    tags: ['PHP', 'MySQL', 'Tailwind CSS', 'JavaScript', 'CRUD']
  },
  {
    id: 7,
    title: 'Flutter Marketplace',
    subtitle: 'Cross-Platform Mobile Application',
    category: 'mobile',
    categoryName: 'CROSS-PLATFORM MOBILE',
    badge: 'MOBILE DEV',
    description: 'Aplikasi Android marketplace dengan arsitektur modular dan reusable components untuk performa transaksi yang cepat.',
    tags: ['Flutter', 'Dart', 'Mobile Dev', 'Reusable Components']
  }
];

const filteredProjects = computed(() => {
  if (activeCategory.value === 'all') return projects;
  return projects.filter(p => p.category === activeCategory.value);
});

// All Updated Experiences
const experiences = [
  {
    role: 'UI/UX Designer (Freelance)',
    company: 'Independent & Client Projects',
    period: 'Freelance / On-Demand',
    featured: true,
    points: [
      'Merancang desain antarmuka (UI) dan pengalaman pengguna (UX) untuk kebutuhan aplikasi atau website.',
      'Membuat user flow, wireframe, dan prototype menggunakan Figma.',
      'Menerapkan prinsip Design Thinking untuk menghasilkan desain yang berorientasi pada kebutuhan pengguna.',
      'Mengembangkan desain berdasarkan kebutuhan proyek dan masukan dari klien.'
    ],
    tags: ['UI/UX Design', 'Figma', 'Design Thinking', 'User Flow', 'Wireframing', 'Prototyping', 'Client Collaboration']
  },
  {
    role: 'Admin Sales Support (Freelance)',
    company: 'PT Prisma Cemerlang Motors',
    period: 'Freelance / On-Demand',
    description: 'Bertanggung jawab dalam pengelolaan database transaksi penjualan, pengarsipan dokumen digital administrasi perusahaan, serta support operasional data bisnis yang cepat dan akurat.',
    tags: ['Data Management', 'Administration', 'Spreadsheet', 'Workflow Analysis']
  },
  {
    role: 'Wakil Kepala Departemen HR',
    company: 'Veteran Robotics Team',
    period: 'Organizational Leadership',
    description: 'Memimpin koordinasi tim, mentoring anggota baru, evaluasi kinerja personil, serta perancangan program regenerasi dan recruitment SDM di bidang teknologi robotika.',
    tags: ['HR Management', 'Team Leadership', 'Mentoring', 'Talent Development']
  },
  {
    role: 'Mentor UI/UX Design',
    company: 'ISCOM (Information System Community)',
    period: 'Mentorship',
    description: 'Membimbing mahasiswa dan anggota komunitas dalam fundamental UI/UX, Design Thinking, wireframing, interactive prototyping menggunakan Figma, serta implementasi prinsip usability.',
    tags: ['Figma', 'UI/UX Mentoring', 'Design Thinking', 'Usability Testing']
  },
  {
    role: 'Pemateri Bahasa Pemrograman',
    company: 'Akademik Kampus',
    period: 'Lecturing & Workshop',
    description: 'Mengajar mahasiswa baru mengenai algoritma dasar, logika pemrograman Java, dan sesi live coding interaktif untuk mempermudah pemahaman fundamental software development.',
    tags: ['Java', 'Algorithm', 'Public Speaking', 'Code Review']
  }
];

// All Updated Achievements (Including Technotainment & ITFEST 2026)
const achievements = [
  {
    year: '2026',
    title: 'Juara 1 UI/UX Design',
    event: 'ISOFEST 2026 Nasional',
    description: 'Meraih peringkat pertama dalam kompetisi UI/UX nasional melalui solusi desain aplikasi inovatif dengan metodologi Design Thinking & validasi user yang komprehensif.'
  },
  {
    year: '2026',
    title: 'GrandFinalis UI/UX Designer',
    event: 'Technotainment 2026 Nasional',
    description: 'Berhasil melaju sebagai Grand Finalis pada cabang lomba UI/UX Designer melalui perancangan solusi produk digital yang inovatif dan berorientasi pada kebutuhan pengguna.'
  },
  {
    year: '2026',
    title: 'Juara 3 UI/UX Design',
    event: 'International Hackfest 2026',
    description: 'Berhasil meraih Juara 3 pada ajang kompetisi internasional dengan menyajikan purwarupa digital yang fokus pada aksesibilitas dan kemudahan penggunaan pengguna.'
  },
  {
    year: '2026',
    title: 'Finalis Web Development',
    event: 'ITFEST 2026 Nasional',
    description: 'Meraih predikat Finalis dalam kompetisi rekayasa web nasional berkat pengembangan aplikasi web modern yang responsif, terstruktur, dan berkinerja tinggi.'
  },
  {
    year: '2025',
    title: 'Finalis Kontes Kapal Indonesia',
    event: 'KKI 2025 Puspresnas',
    description: 'Menjadi finalis divisi Electrical Remote Control tingkat nasional dan berkontribusi aktif dalam perancangan desain konsep serta integrasi sistem kapal robotik.'
  }
];
</script>
