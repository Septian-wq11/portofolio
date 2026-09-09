<template>
  <div class="relative min-h-screen bg-[#FAF6F0] text-[#302419] overflow-x-hidden selection:bg-[#800F19] selection:text-white">
    <!-- Ambient Background Glows -->
    <div class="fixed inset-0 pointer-events-none z-0 overflow-hidden">
      <div class="absolute -top-[20%] -left-[10%] w-[650px] h-[650px] rounded-full bg-[#800F19]/10 blur-[140px]"></div>
      <div class="absolute top-[40%] -right-[10%] w-[550px] h-[550px] rounded-full bg-[#C1A277]/20 blur-[130px]"></div>
      <div class="absolute -bottom-[10%] left-[20%] w-[700px] h-[700px] rounded-full bg-[#800F19]/8 blur-[150px]"></div>
      <div class="absolute inset-0 bg-grid-pattern opacity-40"></div>
    </div>

    <!-- Sticky Navigation Bar -->
    <header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 backdrop-blur-md bg-[#FAF6F0]/85 border-b border-[#E6D7BD]/60 shadow-xs">
      <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
        <!-- Logo -->
        <a href="#" class="flex items-center gap-3 group">
          <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-[#800F19] to-[#46080E] flex items-center justify-center text-white font-bold text-base shadow-md shadow-[#800F19]/25 group-hover:scale-105 transition-transform">
            ST
          </div>
          <div class="flex flex-col">
            <span class="font-extrabold text-sm sm:text-base tracking-wide text-[#46080E]">SEPTIAN LISTIA TRI CAHYO</span>
            <span class="text-[10px] sm:text-xs font-semibold tracking-wider text-[#A7865C] uppercase">Portofolio</span>
          </div>
        </a>

        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center gap-7 text-sm font-medium">
          <a href="#about" class="text-[#594633] hover:text-[#800F19] transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#800F19] hover:after:w-full after:transition-all">About</a>
          <a href="#experience" class="text-[#594633] hover:text-[#800F19] transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#800F19] hover:after:w-full after:transition-all">Experience</a>
          <a href="#projects" class="text-[#594633] hover:text-[#800F19] transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#800F19] hover:after:w-full after:transition-all">Projects</a>
          <a href="#skills" class="text-[#594633] hover:text-[#800F19] transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#800F19] hover:after:w-full after:transition-all">Skills</a>
          <a href="#achievements" class="text-[#594633] hover:text-[#800F19] transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#800F19] hover:after:w-full after:transition-all">Achievements</a>
          <a href="#contact" class="text-[#594633] hover:text-[#800F19] transition-colors relative py-1 after:content-[''] after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-[#800F19] hover:after:w-full after:transition-all">Contact</a>
        </div>

        <!-- Action Button (Hire / CV) -->
        <div class="hidden sm:flex items-center gap-3">
          <a 
            href="#contact" 
            class="px-4 py-2 rounded-full bg-gradient-to-r from-[#800F19] to-[#A41623] hover:from-[#640D14] hover:to-[#800F19] text-white text-xs sm:text-sm font-semibold tracking-wide shadow-md shadow-[#800F19]/25 hover:shadow-lg hover:-translate-y-0.5 transition-all duration-300 flex items-center gap-1.5"
          >
            <span>Let's Talk</span>
            <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"/></svg>
          </a>
        </div>

        <!-- Mobile Menu Toggle -->
        <button 
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden p-2 rounded-lg text-[#46080E] hover:bg-[#F1E9D8] transition-colors"
          aria-label="Toggle Menu"
        >
          <svg v-if="!mobileMenuOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/></svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/></svg>
        </button>
      </nav>

      <!-- Mobile Dropdown Menu -->
      <div v-show="mobileMenuOpen" class="md:hidden bg-[#FAF6F0] border-b border-[#E6D7BD] px-6 py-4 space-y-3 shadow-xl">
        <a @click="mobileMenuOpen = false" href="#about" class="block py-2 text-[#46080E] font-medium hover:text-[#800F19]">About</a>
        <a @click="mobileMenuOpen = false" href="#experience" class="block py-2 text-[#46080E] font-medium hover:text-[#800F19]">Experience</a>
        <a @click="mobileMenuOpen = false" href="#projects" class="block py-2 text-[#46080E] font-medium hover:text-[#800F19]">Projects</a>
        <a @click="mobileMenuOpen = false" href="#skills" class="block py-2 text-[#46080E] font-medium hover:text-[#800F19]">Skills</a>
        <a @click="mobileMenuOpen = false" href="#achievements" class="block py-2 text-[#46080E] font-medium hover:text-[#800F19]">Achievements</a>
        <a @click="mobileMenuOpen = false" href="#contact" class="block py-2 text-[#46080E] font-medium hover:text-[#800F19]">Contact</a>
        <a @click="mobileMenuOpen = false" href="#contact" class="block text-center w-full py-2.5 rounded-full bg-[#800F19] text-white font-medium shadow-md">Hire / Contact Me</a>
      </div>
    </header>

    <!-- Main Container -->
    <main class="relative z-10 pt-20 sm:pt-24">
      <!-- HERO SECTION -->
      <section class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 lg:py-14 flex flex-col-reverse lg:flex-row items-center justify-between gap-8 lg:gap-12 min-h-[75vh]">
        <!-- Hero Text -->
        <div class="flex-1 text-center lg:text-left space-y-5">
          <!-- Availability Badge for HRD -->
          <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-white/90 border border-[#E6D7BD] shadow-xs backdrop-blur-md">
            <span class="w-2.5 h-2.5 rounded-full bg-emerald-500 animate-pulse"></span>
            <span class="text-xs font-semibold text-[#800F19] tracking-wide uppercase">Open for Work / Internship</span>
          </div>

          <div class="space-y-1.5">
            <h2 class="text-xs sm:text-sm font-semibold tracking-wider text-[#A7865C] uppercase">
              Hello Recruiter & Visitor, I'm
            </h2>
            <h1 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-[#46080E] tracking-tight leading-[1.15]">
              Septian Listia <span class="bg-gradient-to-r from-[#800F19] to-[#DF9E25] bg-clip-text text-transparent">Tri Cahyo</span>
            </h1>
          </div>

          <!-- Roles Pills -->
          <div class="flex flex-wrap justify-center lg:justify-start gap-2 pt-1">
            <span class="px-4 py-1.5 rounded-lg bg-[#800F19]/10 text-[#800F19] font-semibold text-xs sm:text-sm border border-[#800F19]/20">UI/UX Designer</span>
            <span class="px-4 py-1.5 rounded-lg bg-[#C1A277]/20 text-[#6E553C] font-semibold text-xs sm:text-sm border border-[#C1A277]/30">Front-End Developer</span>
            <span class="px-4 py-1.5 rounded-lg bg-white text-[#46080E] font-semibold text-xs sm:text-sm border border-[#E6D7BD] shadow-xs">System Analyst</span>
          </div>

          <!-- Summary Bio -->
          <p class="text-sm sm:text-base text-[#594633] max-w-2xl leading-relaxed mx-auto lg:mx-0">
            Mahasiswa Sistem Informasi UPN Veteran Jawa Timur berprestasi nasional yang berfokus membangun produk digital yang intuitif, estetik, dan berorientasi solusi bisnis nyata melalui pendekatan <strong class="text-[#800F19]">Design Thinking</strong> dan rekayasa web modern.
          </p>

          <!-- HRD Quick Action Buttons -->
          <div class="flex flex-wrap justify-center lg:justify-start items-center gap-3 pt-2">
            <a 
              href="#projects" 
              class="px-6 py-3 rounded-xl bg-gradient-to-r from-[#800F19] to-[#A41623] hover:from-[#640D14] hover:to-[#800F19] text-white font-bold text-sm tracking-wide shadow-md shadow-[#800F19]/25 hover:shadow-lg hover:-translate-y-0.5 transition-all duration-300 flex items-center gap-2"
            >
              <span>Explore My Work</span>
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/></svg>
            </a>

            <a 
              href="#contact" 
              class="px-5 py-3 rounded-xl bg-white hover:bg-[#F8F4EB] text-[#800F19] font-bold text-sm tracking-wide border border-[#E6D7BD] shadow-xs hover:shadow-sm hover:-translate-y-0.5 transition-all duration-300 flex items-center gap-2"
            >
              <svg class="w-4 h-4 text-[#800F19]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/></svg>
              <span>Contact & Resume</span>
            </a>
          </div>

          <!-- Quick Stats / Trust Indicators -->
          <div class="pt-4 grid grid-cols-3 gap-4 border-t border-[#E6D7BD]/80 max-w-lg mx-auto lg:mx-0">
            <div class="text-center lg:text-left">
              <div class="text-2xl sm:text-3xl font-extrabold text-[#800F19]">3+</div>
              <div class="text-[11px] sm:text-xs font-medium text-[#876A47] uppercase tracking-wider">National Awards</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="text-2xl sm:text-3xl font-extrabold text-[#800F19]">7+</div>
              <div class="text-[11px] sm:text-xs font-medium text-[#876A47] uppercase tracking-wider">Featured Projects</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="text-2xl sm:text-3xl font-extrabold text-[#800F19]">4+</div>
              <div class="text-[11px] sm:text-xs font-medium text-[#876A47] uppercase tracking-wider">Org & Mentoring</div>
            </div>
          </div>
        </div>

        <!-- Hero Visual / Photo -->
        <div class="flex-1 flex justify-center items-center relative">
          <div class="relative w-64 h-64 sm:w-72 sm:h-72 lg:w-[330px] lg:h-[330px]">
            <!-- Outer Accent Border -->
            <div class="absolute -inset-2 rounded-full bg-gradient-to-tr from-[#800F19]/25 via-[#C1A277]/20 to-[#FAF6F0] p-1 shadow-xl shadow-[#800F19]/10"></div>
            
            <!-- Photo Container with optimal scale & positioning -->
            <div class="relative w-full h-full rounded-full overflow-hidden bg-[#FAF6F0] border-4 border-white shadow-xl group flex items-center justify-center">
              <img 
                :src="profileImg || './FotoProfile.png'" 
                @error="$event.target.src = './FotoProfile.png'"
                alt="Septian Listia Tri Cahyo" 
                class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500"
                style="object-position: 50% 28%; transform: scale(1.22);"
              />
            </div>
          </div>
        </div>
      </section>

      <!-- ABOUT SECTION -->
      <section id="about" class="py-20 bg-gradient-to-b from-transparent via-[#F8F4EB] to-transparent">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-2xl mx-auto mb-16 space-y-3">
            <span class="text-xs font-bold uppercase tracking-widest text-[#800F19]">Get To Know Me</span>
            <h2 class="text-3xl sm:text-4xl font-extrabold text-[#46080E]">About & Core Competencies</h2>
            <div class="w-16 h-1 bg-[#800F19] mx-auto rounded-full"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Card 1: Education -->
            <div class="glass-card rounded-3xl p-8 shadow-sm hover:shadow-xl hover:border-[#800F19]/30 transition-all duration-300 group">
              <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-[#800F19] to-[#640D14] flex items-center justify-center text-white mb-6 shadow-md shadow-[#800F19]/20 group-hover:scale-110 transition-transform">
                <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5"/></svg>
              </div>
              <h3 class="text-xl font-bold text-[#46080E] mb-3">Pendidikan Formal</h3>
              <p class="text-sm font-semibold text-[#800F19] mb-2">S1 Sistem Informasi</p>
              <p class="text-xs text-[#876A47] font-medium mb-4">UPN "Veteran" Jawa Timur</p>
              <p class="text-[#594633] text-sm leading-relaxed">
                Memperdalam perpaduan antara analisis kebutuhan sistem, manajemen teknologi informasi, dan rekayasa antarmuka pengguna berbasis riset.
              </p>
            </div>

            <!-- Card 2: Design Philosophy -->
            <div class="glass-card rounded-3xl p-8 shadow-sm hover:shadow-xl hover:border-[#800F19]/30 transition-all duration-300 group">
              <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-[#C1A277] to-[#876A47] flex items-center justify-center text-white mb-6 shadow-md shadow-[#C1A277]/30 group-hover:scale-110 transition-transform">
                <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01"/></svg>
              </div>
              <h3 class="text-xl font-bold text-[#46080E] mb-3">UI/UX & Design Thinking</h3>
              <p class="text-sm font-semibold text-[#800F19] mb-2">Human-Centered Design</p>
              <p class="text-xs text-[#876A47] font-medium mb-4">Figma, Usability & Prototyping</p>
              <p class="text-[#594633] text-sm leading-relaxed">
                Membangun flow yang mulus dan visual yang bernilai estetika tinggi, didasari riset pengguna, wireframing, dan usability testing.
              </p>
            </div>

            <!-- Card 3: Engineering & Analysis -->
            <div class="glass-card rounded-3xl p-8 shadow-sm hover:shadow-xl hover:border-[#800F19]/30 transition-all duration-300 group md:col-span-2 lg:col-span-1">
              <div class="w-14 h-14 rounded-2xl bg-gradient-to-br from-[#46080E] to-[#2B0408] flex items-center justify-center text-white mb-6 shadow-md shadow-[#46080E]/30 group-hover:scale-110 transition-transform">
                <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/></svg>
              </div>
              <h3 class="text-xl font-bold text-[#46080E] mb-3">Front-End & Analysis</h3>
              <p class="text-sm font-semibold text-[#800F19] mb-2">Modern Web & Clean Architecture</p>
              <p class="text-xs text-[#876A47] font-medium mb-4">Vue, Tailwind, PHP & System Flow</p>
              <p class="text-[#594633] text-sm leading-relaxed">
                Menerjemahkan ide desain menjadi kode responsif, performan tinggi, dan ramah SEO dengan maintainability yang rapi.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- EXPERIENCE SECTION -->
      <section id="experience" class="py-20">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-2xl mx-auto mb-16 space-y-3">
            <span class="text-xs font-bold uppercase tracking-widest text-[#800F19]">Career Journey</span>
            <h2 class="text-3xl sm:text-4xl font-extrabold text-[#46080E]">Professional & Organizational Experience</h2>
            <div class="w-16 h-1 bg-[#800F19] mx-auto rounded-full"></div>
          </div>

          <div class="relative pl-6 sm:pl-10 space-y-10 border-l-2 border-[#E6D7BD]">
            <div 
              v-for="(exp, index) in experiences" 
              :key="index"
              class="relative group"
            >
              <!-- Timeline Dot -->
              <div class="absolute -left-[31px] sm:-left-[47px] top-1.5 w-6 h-6 rounded-full bg-white border-4 border-[#800F19] group-hover:scale-125 group-hover:bg-[#800F19] transition-all duration-300"></div>

              <div class="glass-card rounded-2xl p-6 sm:p-8 hover:shadow-lg hover:border-[#800F19]/40 transition-all duration-300">
                <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 mb-3">
                  <div>
                    <h3 class="text-lg sm:text-xl font-bold text-[#46080E] group-hover:text-[#800F19] transition-colors">{{ exp.role }}</h3>
                    <div class="text-sm font-semibold text-[#876A47]">{{ exp.company }}</div>
                  </div>
                  <span class="inline-block px-3 py-1 rounded-full text-xs font-bold tracking-wide bg-[#800F19]/10 text-[#800F19] self-start sm:self-auto">
                    {{ exp.period }}
                  </span>
                </div>
                <p class="text-[#594633] text-sm leading-relaxed mb-4">
                  {{ exp.description }}
                </p>
                <div class="flex flex-wrap gap-2">
                  <span 
                    v-for="(tag, tIndex) in exp.tags" 
                    :key="tIndex"
                    class="px-2.5 py-0.5 rounded-md bg-[#FAF6F0] text-[11px] font-semibold text-[#6E553C] border border-[#E6D7BD]"
                  >
                    {{ tag }}
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- PROJECTS SHOWCASE SECTION -->
      <section id="projects" class="py-20 bg-gradient-to-b from-[#F8F4EB] via-[#FAF6F0] to-[#F8F4EB]">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-2xl mx-auto mb-12 space-y-3">
            <span class="text-xs font-bold uppercase tracking-widest text-[#800F19]">Featured Portfolio</span>
            <h2 class="text-3xl sm:text-4xl font-extrabold text-[#46080E]">Selected Projects & Case Studies</h2>
            <div class="w-16 h-1 bg-[#800F19] mx-auto rounded-full"></div>
          </div>

          <!-- Project Filter Tabs -->
          <div class="flex flex-wrap justify-center items-center gap-3 mb-12">
            <button 
              v-for="cat in projectCategories" 
              :key="cat.id"
              @click="activeCategory = cat.id"
              :class="[
                'px-5 py-2 rounded-full text-xs sm:text-sm font-bold transition-all duration-300 cursor-pointer',
                activeCategory === cat.id 
                  ? 'bg-[#800F19] text-white shadow-md shadow-[#800F19]/25 scale-105' 
                  : 'bg-white text-[#6E553C] hover:bg-[#F1E9D8] border border-[#E6D7BD]'
              ]"
            >
              {{ cat.label }}
            </button>
          </div>

          <!-- Project Cards Grid -->
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div 
              v-for="(project, index) in filteredProjects" 
              :key="project.id"
              class="glass-card rounded-3xl overflow-hidden border border-[#E6D7BD] hover:border-[#800F19]/40 hover:shadow-xl hover:-translate-y-1.5 transition-all duration-300 flex flex-col group"
            >
              <!-- Project Header Badge & Accent Bar -->
              <div :class="`h-44 bg-gradient-to-br ${project.gradient} p-6 flex flex-col justify-between relative overflow-hidden`">
                <div class="absolute -right-8 -bottom-8 w-32 h-32 rounded-full bg-white/10 blur-xl"></div>
                <div class="flex justify-between items-start z-10">
                  <span class="px-3 py-1 rounded-full bg-black/25 backdrop-blur-md text-white text-xs font-semibold uppercase tracking-wider">
                    {{ project.category }}
                  </span>
                </div>
                <div class="z-10">
                  <h3 class="text-2xl font-black text-white tracking-wide drop-shadow-sm">{{ project.title }}</h3>
                  <p class="text-xs text-white/80 font-medium">{{ project.subtitle }}</p>
                </div>
              </div>

              <!-- Project Body -->
              <div class="p-6 flex-1 flex flex-col justify-between space-y-4">
                <p class="text-[#594633] text-sm leading-relaxed">
                  {{ project.description }}
                </p>

                <div>
                  <div class="text-[11px] font-bold text-[#A7865C] uppercase tracking-wider mb-2">Highlights & Tech</div>
                  <div class="flex flex-wrap gap-1.5">
                    <span 
                      v-for="(tech, tIndex) in project.tags" 
                      :key="tIndex"
                      class="px-2.5 py-1 rounded-lg bg-[#FAF6F0] text-[#6E553C] text-xs font-semibold border border-[#E6D7BD]"
                    >
                      {{ tech }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- SKILLS MATRIX SECTION -->
      <section id="skills" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-2xl mx-auto mb-16 space-y-3">
            <span class="text-xs font-bold uppercase tracking-widest text-[#800F19]">Technical Arsenal</span>
            <h2 class="text-3xl sm:text-4xl font-extrabold text-[#46080E]">Skills & Tools Mastery</h2>
            <div class="w-16 h-1 bg-[#800F19] mx-auto rounded-full"></div>
            <p class="text-sm text-[#594633]">Perangkat dan teknologi yang siap digunakan untuk kebutuhan pengembangan produk digital perusahaan Anda.</p>
          </div>

          <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-5">
            <div 
              v-for="(skill, index) in skills" 
              :key="index"
              class="glass-card rounded-2xl p-5 text-center border border-[#E6D7BD] hover:border-[#800F19] hover:shadow-xl hover:-translate-y-1.5 transition-all duration-300 group flex flex-col items-center justify-center space-y-3"
            >
              <div class="w-14 h-14 rounded-xl bg-[#FAF6F0] p-2.5 flex items-center justify-center border border-[#E6D7BD] group-hover:scale-110 group-hover:border-[#800F19]/40 transition-all shadow-xs">
                <img :src="skill.icon" :alt="skill.name" class="w-9 h-9 object-contain" />
              </div>
              <div>
                <h4 class="font-bold text-sm text-[#46080E] group-hover:text-[#800F19] transition-colors">{{ skill.name }}</h4>
                <span class="text-[10px] font-semibold text-[#876A47] uppercase tracking-wider">{{ skill.level }}</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- ACHIEVEMENTS SECTION (HRD High Impact) -->
      <section id="achievements" class="py-20 bg-gradient-to-b from-[#FAF6F0] via-[#F8F4EB] to-[#FAF6F0]">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="text-center max-w-2xl mx-auto mb-16 space-y-3">
            <span class="text-xs font-bold uppercase tracking-widest text-[#800F19]">Proven Excellence</span>
            <h2 class="text-3xl sm:text-4xl font-extrabold text-[#46080E]">Honors & Competitions</h2>
            <div class="w-16 h-1 bg-[#800F19] mx-auto rounded-full"></div>
            <p class="text-sm text-[#594633]">Bukti dedikasi, daya saing, dan kemampuan problem solving di tingkat nasional & internasional.</p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div 
              v-for="(achieve, index) in achievements" 
              :key="index"
              class="relative bg-white rounded-3xl p-8 border-2 border-[#E6D7BD] hover:border-[#800F19] shadow-md hover:shadow-2xl transition-all duration-300 flex flex-col justify-between group"
            >
              <div class="space-y-4">
                <div class="flex items-center justify-between">
                  <div class="text-4xl">{{ achieve.medal }}</div>
                  <span class="px-3 py-1 rounded-full text-xs font-bold bg-[#800F19]/10 text-[#800F19] border border-[#800F19]/20">
                    {{ achieve.year }}
                  </span>
                </div>
                <h3 class="text-xl font-extrabold text-[#46080E] group-hover:text-[#800F19] transition-colors">
                  {{ achieve.title }}
                </h3>
                <div class="text-xs font-bold uppercase tracking-wider text-[#A7865C]">{{ achieve.event }}</div>
                <p class="text-[#594633] text-sm leading-relaxed">
                  {{ achieve.description }}
                </p>
              </div>

              <div class="pt-6 mt-6 border-t border-[#F1E9D8] flex items-center gap-2 text-xs font-bold text-[#800F19]">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"/></svg>
                <span>Verified Achievement</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- CONTACT & HRD CTA SECTION -->
      <section id="contact" class="py-20 relative overflow-hidden">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="bg-gradient-to-br from-[#46080E] via-[#640D14] to-[#2B0408] rounded-3xl p-8 sm:p-14 text-white shadow-2xl relative overflow-hidden border border-white/10">
            <!-- Decorative Glow Elements -->
            <div class="absolute -right-20 -bottom-20 w-80 h-80 rounded-full bg-[#DF9E25]/20 blur-3xl"></div>
            <div class="absolute -left-20 -top-20 w-80 h-80 rounded-full bg-[#800F19]/40 blur-3xl"></div>

            <div class="relative z-10 grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
              <div class="space-y-6">
                <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/10 text-xs font-semibold text-[#FAF6F0] tracking-wide uppercase border border-white/10">
                  <span>📬</span> Ready for Collaboration
                </div>
                <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight leading-tight">
                  Tertarik Mendiskusikan Peluang Karir atau Proyek?
                </h2>
                <p class="text-white/80 text-sm sm:text-base leading-relaxed">
                  Saya selalu terbuka untuk tawaran pekerjaan full-time, magang (internship), freelance UI/UX & Web Development, atau kolaborasi inovatif lainnya.
                </p>

                <div class="space-y-3 pt-2">
                  <div class="flex items-center gap-3 text-sm text-white/90">
                    <div class="w-8 h-8 rounded-lg bg-white/10 flex items-center justify-center">📧</div>
                    <span>listiaseptian11@gmail.com</span>
                  </div>
                  <div class="flex items-center gap-3 text-sm text-white/90">
                    <div class="w-8 h-8 rounded-lg bg-white/10 flex items-center justify-center">📍</div>
                    <span>Surabaya, Jawa Timur, Indonesia</span>
                  </div>
                  <div class="flex items-center gap-3 text-sm text-white/90">
                    <div class="w-8 h-8 rounded-lg bg-white/10 flex items-center justify-center">🐙</div>
                    <a href="https://github.com/Septian-Wq11" target="_blank" class="hover:underline">github.com/Septian-Wq11</a>
                  </div>
                </div>
              </div>

              <!-- Quick Action Card -->
              <div class="bg-white rounded-2xl p-6 sm:p-8 text-[#302419] shadow-xl space-y-6">
                <h3 class="text-xl font-extrabold text-[#46080E]">Direct Message & Mail</h3>
                <p class="text-xs text-[#6E553C]">Kirim email langsung melalui tombol di bawah atau copy alamat email saya.</p>

                <div class="space-y-3">
                  <a 
                    href="https://mail.google.com/mail/?view=cm&fs=1&to=listiaseptian11@gmail.com" 
                    target="_blank"
                    class="w-full py-3.5 px-6 rounded-xl bg-gradient-to-r from-[#800F19] to-[#A41623] hover:from-[#640D14] hover:to-[#800F19] text-white font-bold text-sm tracking-wide shadow-lg shadow-[#800F19]/25 flex items-center justify-center gap-2 hover:-translate-y-0.5 transition-all"
                  >
                    <span>Send Email via Gmail</span>
                    <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"/></svg>
                  </a>

                  <a 
                    href="mailto:listiaseptian11@gmail.com"
                    class="w-full py-3 px-6 rounded-xl bg-[#F8F4EB] hover:bg-[#F1E9D8] text-[#800F19] font-bold text-xs tracking-wide border border-[#E6D7BD] flex items-center justify-center gap-2 transition-all"
                  >
                    <span>Open Default Mail Client</span>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- FOOTER -->
    <footer class="bg-[#FAF6F0] border-t border-[#E6D7BD] py-10 text-center text-xs text-[#876A47] space-y-2">
      <div class="max-w-7xl mx-auto px-4">
        <p class="font-semibold text-[#46080E]">© 2026 Septian Listia Tri Cahyo. All rights reserved.</p>
        <p class="text-[11px]">Crafted with Laravel, Vue 3, & Tailwind CSS • Maroon & Warm Cream Edition</p>
      </div>
    </footer>

    <!-- INTERACTIVE PROJECT CASE MODAL -->
    <div 
      v-if="selectedProject" 
      class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/60 backdrop-blur-sm animate-fadeIn"
      @click.self="selectedProject = null"
    >
      <div class="bg-white rounded-3xl max-w-2xl w-full max-h-[90vh] overflow-y-auto shadow-2xl border border-[#E6D7BD] flex flex-col">
        <!-- Modal Header -->
        <div :class="`bg-gradient-to-r ${selectedProject.gradient} p-6 sm:p-8 text-white relative`">
          <button 
            @click="selectedProject = null"
            class="absolute top-4 right-4 w-9 h-9 rounded-full bg-black/30 hover:bg-black/50 flex items-center justify-center text-white transition-colors"
          >
            ✕
          </button>
          <span class="px-3 py-1 rounded-full bg-black/30 text-[11px] font-bold uppercase tracking-wider">
            {{ selectedProject.category }}
          </span>
          <h3 class="text-2xl sm:text-3xl font-extrabold mt-3">{{ selectedProject.title }}</h3>
          <p class="text-sm text-white/80 font-medium">{{ selectedProject.subtitle }}</p>
        </div>

        <!-- Modal Body -->
        <div class="p-6 sm:p-8 space-y-6">
          <div>
            <h4 class="text-xs font-bold uppercase tracking-wider text-[#800F19] mb-2">Project Overview</h4>
            <p class="text-sm text-[#594633] leading-relaxed">{{ selectedProject.description }}</p>
          </div>

          <div v-if="selectedProject.problem">
            <h4 class="text-xs font-bold uppercase tracking-wider text-[#800F19] mb-2">Problem Statement & User Need</h4>
            <p class="text-sm text-[#594633] leading-relaxed">{{ selectedProject.problem }}</p>
          </div>

          <div v-if="selectedProject.solution">
            <h4 class="text-xs font-bold uppercase tracking-wider text-[#800F19] mb-2">Proposed Solution & Key Features</h4>
            <p class="text-sm text-[#594633] leading-relaxed">{{ selectedProject.solution }}</p>
          </div>

          <div>
            <h4 class="text-xs font-bold uppercase tracking-wider text-[#800F19] mb-2">Technologies & Tools</h4>
            <div class="flex flex-wrap gap-2">
              <span 
                v-for="(t, i) in selectedProject.tags" 
                :key="i"
                class="px-3 py-1 rounded-lg bg-[#FAF6F0] text-[#800F19] font-bold text-xs border border-[#E6D7BD]"
              >
                {{ t }}
              </span>
            </div>
          </div>
        </div>

        <!-- Modal Footer -->
        <div class="p-6 bg-[#FAF6F0] border-t border-[#E6D7BD] flex justify-end">
          <button 
            @click="selectedProject = null"
            class="px-6 py-2.5 rounded-xl bg-[#800F19] text-white font-bold text-sm hover:bg-[#640D14] transition-colors"
          >
            Close Details
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import profileImg from '/public/FotoProfile.png?url';

const mobileMenuOpen = ref(false);
const activeCategory = ref('all');
const selectedProject = ref(null);

const projectCategories = [
  { id: 'all', label: 'All Works' },
  { id: 'uiux', label: 'UI/UX Design' },
  { id: 'web', label: 'Web Development' },
  { id: 'mobile', label: 'Mobile & IoT' }
];

const experiences = [
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

const projects = [
  {
    id: 1,
    title: 'PILAH',
    subtitle: 'Textile Waste & Upcycling Ecosystem',
    category: 'uiux',
    gradient: 'from-[#800F19] to-[#A41623]',
    description: 'Konsep aplikasi mobile yang dirancang untuk menghubungkan konveksi sebagai penghasil limbah tekstil dengan UMKM upcycling sebagai pengguna bahan baku. Membantu menemukan material limbah, memahami kondisi material, bertransaksi, dan membangun kemitraan berkelanjutan.',
    tags: ['Design Thinking', 'User Research', 'Mobile App', 'E-Commerce', 'Usability Testing']
  },
  {
    id: 2,
    title: 'SIPOSYA',
    subtitle: 'Digital Posyandu Mobile Application',
    category: 'uiux',
    gradient: 'from-[#640D14] to-[#C9182B]',
    description: 'Perancangan UI/UX aplikasi layanan Posyandu berbasis mobile untuk mendigitalkan pencatatan tumbuh kembang balita dan layanan kesehatan masyarakat.',
    tags: ['Figma', 'UI/UX', 'Mobile App', 'Design System', 'User Research']
  },
  {
    id: 2,
    title: 'SIROW',
    subtitle: 'Smart Farming IoT & Water Monitoring',
    category: 'uiux',
    gradient: 'from-[#46080E] to-[#800F19]',
    description: 'Perancangan UI/UX aplikasi smart farming berbasis mobile terintegrasi IoT untuk memonitor debit air, kualitas irigasi, dan otomasi penyiraman pertanian.',
    problem: 'Petani membutuhkan pemantauan parameter air secara efisien tanpa harus memeriksa fisik lahan secara terus-menerus.',
    solution: 'Dashboard monitoring sensor real-time dengan status peringatan dini dan kontrol irigasi otomatis satu sentuhan.',
    tags: ['Figma', 'UI/UX', 'Mobile App', 'IoT Concept', 'Design System']
  },
  {
    id: 3,
    title: 'FLOMART',
    subtitle: 'Plant & Flora Digital Marketplace',
    category: 'uiux',
    gradient: 'from-[#A7865C] to-[#800F19]',
    description: 'Desain marketplace tanaman hias dengan navigasi pencarian visual berdasarkan jenis perawatan, pencahayaan, dan kemudahan transaksi.',
    problem: 'Pecinta tanaman sering kesulitan memilih tanaman yang cocok dengan kondisi ruangan dan iklim rumah.',
    solution: 'Penerapan filter interaktif berdasarkan level perawatan tanaman, integrasi panduan merawat, dan checkout checkout flow yang simpel.',
    tags: ['Figma', 'E-Commerce', 'User Flow', 'Wireframing']
  },
  {
    id: 4,
    title: 'LOUSEL',
    subtitle: 'Mental Health & Emotional Assistant',
    category: 'uiux',
    gradient: 'from-[#640D14] to-[#A41623]',
    description: 'Aplikasi pendamping kesehatan mental yang dilengkapi fitur mood tracking harian, relaksasi terbimbing, dan jurnal emosi.',
    problem: 'Tingginya stigma dan minimnya sarana pelacakan kondisi emosi harian yang nyaman serta aman bagi anak muda.',
    solution: 'Visual UI dengan tone menenangkan, fitur jurnal terenkripsi, dan analitik suasana hati mingguan.',
    tags: ['UI/UX', 'Design Thinking', 'Mobile Prototype', 'HealthTech']
  },
  {
    id: 5,
    title: 'Website Marketplace Tanaman',
    subtitle: 'Full-Stack E-Commerce Web System',
    category: 'web',
    gradient: 'from-[#876A47] to-[#46080E]',
    description: 'Pengembangan website jual-beli tanaman lengkap dengan katalog dinamis, manajemen inventaris produk, dan sistem transaksi terintegrasi.',
    problem: 'Kebutuhan platform web yang cepat, responsif di berbagai ukuran layar, dan mudah dikelola oleh admin.',
    solution: 'Membangun antarmuka modern menggunakan Tailwind CSS & JavaScript dengan backend modular PHP & database MySQL.',
    tags: ['PHP', 'MySQL', 'Tailwind CSS', 'JavaScript', 'CRUD']
  },
  {
    id: 6,
    title: 'Flutter Marketplace App',
    subtitle: 'Cross-Platform Mobile Application',
    category: 'mobile',
    gradient: 'from-[#800F19] to-[#DF9E25]',
    description: 'Aplikasi Android marketplace dengan arsitektur modular dan reusable components untuk performa transaksi yang cepat.',
    problem: 'Perlunya aplikasi mobile dengan rendering yang mulus dan konsumsi memori yang ringan.',
    solution: 'Implementasi widget kustom Flutter yang efisien, navigasi responsif, dan struktur state management yang bersih.',
    tags: ['Flutter', 'Dart', 'Mobile Dev', 'Reusable Components']
  }
];

const skills = [
  { name: 'Figma', level: 'Advanced / Daily', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg' },
  { name: 'Vue.js', level: 'Front-End', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg' },
  { name: 'Tailwind CSS', level: 'Advanced', icon: 'https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg' },
  { name: 'JavaScript', level: 'ES6+ Front-End', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
  { name: 'HTML5', level: 'Semantic HTML', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg' },
  { name: 'CSS3', level: 'Styling & Motion', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg' },
  { name: 'PHP', level: 'Backend Logic', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg' },
  { name: 'MySQL', level: 'Database Analysis', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg' },
  { name: 'Flutter', level: 'Mobile App', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg' },
  { name: 'Java', level: 'Object Oriented', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg' }
];

const achievements = [
  {
    medal: '🥇',
    year: '2026',
    title: 'Juara 1 UI/UX Design',
    event: 'ISOFEST 2026 Nasional',
    description: 'Meraih peringkat pertama dalam kompetisi UI/UX nasional melalui solusi desain aplikasi inovatif dengan metodologi Design Thinking & validasi user yang komprehensif.'
  },
  {
    medal: '🥉',
    year: '2026',
    title: 'Juara 3 UI/UX Design',
    event: 'International Hackfest 2026',
    description: 'Berhasil meraih Juara 3 pada ajang kompetisi internasional dengan menyajikan purwarupa digital yang fokus pada aksesibilitas dan kemudahan penggunaan pengguna.'
  },
  {
    medal: '🚢',
    year: '2025',
    title: 'Finalis Kontes Kapal Indonesia',
    event: 'KKI 2025 Puspresnas',
    description: 'Menjadi finalis divisi Electrical Remote Control tingkat nasional dan berkontribusi aktif dalam perancangan desain konsep serta integrasi sistem kapal robotik.'
  }
];

const filteredProjects = computed(() => {
  if (activeCategory.value === 'all') return projects;
  return projects.filter(p => p.category === activeCategory.value);
});

const openProjectModal = (project) => {
  selectedProject.value = project;
};
</script>

<style scoped>
@keyframes fadeIn {
  from { opacity: 0; transform: scale(0.98); }
  to { opacity: 1; transform: scale(1); }
}

.animate-fadeIn {
  animation: fadeIn 0.2s ease-out forwards;
}
</style>
