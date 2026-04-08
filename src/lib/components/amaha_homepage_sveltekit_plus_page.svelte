<script lang="ts">
  import { onMount } from 'svelte';
  import {
    ArrowRight,
    Brain,
    Building2,
    CalendarDays,
    CheckCircle2,
    ChevronDown,
    ChevronRight,
    CircleCheckBig,
    ClipboardList,
    HeartPulse,
    Leaf,
    MapPinned,
    Menu,
    MessageSquareHeart,
    MoonStar,
    Phone,
    ShieldCheck,
    Sparkles,
    Stethoscope,
    Users,
    Video,
    X
  } from 'lucide-svelte';

  type NavGroup = {
    title: string;
    items: { label: string; href: string }[];
  };

  type ServiceCard = {
    title: string;
    desc: string;
    icon: typeof Brain;
  };

  type ConditionCard = {
    title: string;
    desc: string;
    tag: string;
  };

  const navGroups: NavGroup[] = [
    {
      title: 'Experts',
      items: [
        { label: 'Therapists', href: '#' },
        { label: 'Psychiatrists', href: '#' },
        { label: 'Child and Youth Experts', href: '#' },
        { label: 'Couples Therapists', href: '#' }
      ]
    },
    {
      title: 'About Amaha',
      items: [
        { label: 'About Us', href: '#' },
        { label: 'Careers', href: '#' },
        { label: 'Amaha In Media', href: '#' },
        { label: 'For Therapists', href: '#' },
        { label: 'Contact Us', href: '#' },
        { label: 'Help / FAQs', href: '#' }
      ]
    },
    {
      title: 'Centres',
      items: [
        { label: 'Bengaluru', href: '#' },
        { label: 'Mumbai', href: '#' },
        { label: 'New Delhi', href: '#' }
      ]
    },
    {
      title: 'For Partners',
      items: [
        { label: 'Employee Well-being Programme', href: '#' },
        { label: 'Our Approach & Offerings', href: '#' },
        { label: 'Webinars & Workshops', href: '#' },
        { label: 'College Well-being Programme', href: '#' }
      ]
    }
  ];

  const services: ServiceCard[] = [
    {
      title: 'Adult Therapy',
      desc: 'Private, evidence-based support tailored to anxiety, depression, burnout, and relationship stress.',
      icon: Brain
    },
    {
      title: 'Adult Psychiatry',
      desc: 'Diagnostic evaluation, medication management, and coordinated psychiatric care.',
      icon: Stethoscope
    },
    {
      title: 'Mental Health Hospital',
      desc: 'Structured care for higher-acuity needs with close monitoring and integrated treatment.',
      icon: Building2
    },
    {
      title: 'Children First Services',
      desc: 'Specialized support for children, adolescents, and families across developmental stages.',
      icon: Users
    },
    {
      title: 'Couples Therapy',
      desc: 'Relationship-focused sessions for communication, repair, and shared problem solving.',
      icon: HeartPulse
    },
    {
      title: 'Self-Care',
      desc: 'Practical resources, guided practices, and light-touch tools for everyday mental wellness.',
      icon: Leaf
    }
  ];

  const conditions: ConditionCard[] = [
    {
      title: 'Obsessive Compulsive Disorder (OCD)',
      desc: 'Assessment, therapy, and clinical planning for intrusive thoughts, compulsions, and avoidance.',
      tag: 'Condition'
    },
    {
      title: 'Adult ADHD',
      desc: 'Support for attention, organization, emotional regulation, and adult functioning.',
      tag: 'Condition'
    },
    {
      title: 'Depression',
      desc: 'Screening and treatment pathways for persistent low mood, anhedonia, and fatigue.',
      tag: 'Condition'
    },
    {
      title: 'Anxiety',
      desc: 'Targeted interventions for worry, panic, social anxiety, and stress-related symptoms.',
      tag: 'Condition'
    },
    {
      title: "Women's Health",
      desc: 'Mental health support across hormonal transitions, reproductive health, and life stages.',
      tag: 'Condition'
    },
    {
      title: 'Alcohol Addiction',
      desc: 'Clinical care for dependence, relapse prevention, and long-term recovery planning.',
      tag: 'Condition'
    }
  ];

  const resources = [
    'All Resources',
    'Articles',
    'Videos',
    'Assessments',
    'Support Kits'
  ];

  const trustBadges = [
    { label: 'ISO', sub: 'Certified' },
    { label: 'HIPAA', sub: 'Aligned' },
    { label: 'EU GDPR', sub: 'Ready' }
  ];

  let mobileMenuOpen = false;

  function closeMobileMenu() {
    mobileMenuOpen = false;
  }

  onMount(() => {
    const onKey = (event: KeyboardEvent) => {
      if (event.key === 'Escape') mobileMenuOpen = false;
    };
    window.addEventListener('keydown', onKey);
    return () => window.removeEventListener('keydown', onKey);
  });
</script>

<svelte:head>
  <title>Amaha-inspired mental healthcare homepage</title>
  <meta
    name="description"
    content="A high-fidelity SvelteKit recreation inspired by the Amaha healthcare homepage structure and visual rhythm."
  />
</svelte:head>

<div class="min-h-screen bg-[#f7f6f2] text-[#18212b]">
  <header class="sticky top-0 z-50 border-b border-black/5 bg-white/90 backdrop-blur-xl">
    <div class="mx-auto flex max-w-7xl items-center justify-between px-4 py-4 sm:px-6 lg:px-8">
      <div class="flex items-center gap-3">
        <div class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#10324a] text-white shadow-sm">
          <MessageSquareHeart size={20} />
        </div>
        <div>
          <div class="text-[15px] font-semibold tracking-tight">Amaha</div>
          <div class="text-xs text-slate-500">Mental healthcare ecosystem</div>
        </div>
      </div>

      <nav class="hidden items-center gap-8 lg:flex">
        <a href="#experts" class="text-sm text-slate-700 transition hover:text-[#10324a]">Experts</a>
        <a href="#services" class="text-sm text-slate-700 transition hover:text-[#10324a]">Services</a>
        <a href="#centres" class="text-sm text-slate-700 transition hover:text-[#10324a]">Centres</a>
        <a href="#resources" class="text-sm text-slate-700 transition hover:text-[#10324a]">Resources</a>
        <a href="#conditions" class="text-sm text-slate-700 transition hover:text-[#10324a]">Conditions</a>
      </nav>

      <div class="hidden items-center gap-3 lg:flex">
        <a
          href="#contact"
          class="rounded-full border border-slate-300 px-4 py-2 text-sm font-medium text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
        >
          Contact
        </a>
        <a
          href="#find-expert"
          class="inline-flex items-center gap-2 rounded-full bg-[#10324a] px-5 py-2.5 text-sm font-semibold text-white shadow-sm transition hover:bg-[#0b2535]"
        >
          Find the right expert <ArrowRight size={16} />
        </a>
      </div>

      <button
        class="inline-flex h-11 w-11 items-center justify-center rounded-2xl border border-slate-300 bg-white text-slate-700 lg:hidden"
        aria-label="Open menu"
        on:click={() => (mobileMenuOpen = true)}
      >
        <Menu size={20} />
      </button>
    </div>

    {#if mobileMenuOpen}
      <div class="fixed inset-0 z-50 bg-black/40 lg:hidden" on:click={closeMobileMenu} aria-hidden="true"></div>
      <aside class="fixed right-0 top-0 z-[60] h-full w-[92vw] max-w-md overflow-y-auto bg-white shadow-2xl lg:hidden">
        <div class="flex items-center justify-between border-b border-slate-200 px-5 py-4">
          <div class="flex items-center gap-3">
            <div class="flex h-10 w-10 items-center justify-center rounded-2xl bg-[#10324a] text-white">
              <MessageSquareHeart size={18} />
            </div>
            <div class="font-semibold">Amaha</div>
          </div>
          <button
            class="inline-flex h-10 w-10 items-center justify-center rounded-xl border border-slate-200"
            aria-label="Close menu"
            on:click={closeMobileMenu}
          >
            <X size={18} />
          </button>
        </div>

        <div class="space-y-8 px-5 py-6">
          {#each navGroups as group}
            <section>
              <h3 class="mb-3 text-xs font-semibold uppercase tracking-[0.22em] text-slate-500">{group.title}</h3>
              <div class="grid gap-2">
                {#each group.items as item}
                  <a
                    href={item.href}
                    class="flex items-center justify-between rounded-2xl bg-slate-50 px-4 py-3 text-sm font-medium text-slate-700"
                  >
                    <span>{item.label}</span>
                    <ChevronRight size={16} class="text-slate-400" />
                  </a>
                {/each}
              </div>
            </section>
          {/each}
          <a
            href="#find-expert"
            class="flex items-center justify-center gap-2 rounded-full bg-[#10324a] px-5 py-3 font-semibold text-white"
          >
            Find the right expert <ArrowRight size={16} />
          </a>
        </div>
      </aside>
    {/if}
  </header>

  <main>
    <section class="relative overflow-hidden">
      <div class="absolute inset-0">
        <div class="absolute -left-32 top-14 h-80 w-80 rounded-full bg-[#dcece7] blur-3xl"></div>
        <div class="absolute right-0 top-20 h-96 w-96 rounded-full bg-[#e6ddd0] blur-3xl"></div>
        <div class="absolute bottom-0 left-1/2 h-72 w-72 -translate-x-1/2 rounded-full bg-[#d7e2ec] blur-3xl"></div>
      </div>

      <div class="relative mx-auto grid max-w-7xl gap-10 px-4 pb-16 pt-10 sm:px-6 lg:grid-cols-12 lg:px-8 lg:pb-24 lg:pt-14">
        <div class="lg:col-span-6 lg:pt-10">
          <div class="mb-5 inline-flex items-center gap-2 rounded-full border border-[#10324a]/10 bg-white px-4 py-2 text-sm text-slate-700 shadow-sm">
            <Sparkles size={16} class="text-[#10324a]" />
            For every age, concern, and stage of care
          </div>

          <h1 class="max-w-2xl text-4xl font-semibold tracking-tight text-[#12222f] sm:text-5xl lg:text-6xl">
            A mental healthcare ecosystem for the way we live, feel, and connect
          </h1>

          <p class="mt-6 max-w-2xl text-lg leading-8 text-slate-600 sm:text-xl">
            We follow a bio-psycho-social model because your body, mind, and environment all shape how you feel.
            Our care supports every part of your life, not just symptoms.
          </p>

          <div class="mt-8 flex flex-col gap-4 sm:flex-row">
            <a
              id="find-expert"
              href="#contact"
              class="inline-flex items-center justify-center gap-2 rounded-full bg-[#10324a] px-6 py-3.5 text-sm font-semibold text-white shadow-lg shadow-[#10324a]/20 transition hover:translate-y-[-1px] hover:bg-[#0b2535]"
            >
              Find the right expert <ArrowRight size={16} />
            </a>
            <a
              href="#services"
              class="inline-flex items-center justify-center gap-2 rounded-full border border-slate-300 bg-white px-6 py-3.5 text-sm font-semibold text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
            >
              Explore services <ChevronDown size={16} />
            </a>
          </div>

          <div class="mt-10 grid gap-4 sm:grid-cols-3">
            <div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <Video size={18} />
                </div>
                <div>
                  <div class="text-sm font-semibold">In-person & online</div>
                  <div class="text-xs text-slate-500">Flexible care formats</div>
                </div>
              </div>
            </div>
            <div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <CalendarDays size={18} />
                </div>
                <div>
                  <div class="text-sm font-semibold">For every age</div>
                  <div class="text-xs text-slate-500">Individuals, families, organisations</div>
                </div>
              </div>
            </div>
            <div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <ShieldCheck size={18} />
                </div>
                <div>
                  <div class="text-sm font-semibold">Private and secure</div>
                  <div class="text-xs text-slate-500">Trust-first care</div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="lg:col-span-6 lg:pl-6">
          <div class="relative mx-auto max-w-xl">
            <div class="absolute -left-3 top-8 h-full w-full rounded-[2rem] border border-white/70 bg-white/60 shadow-[0_20px_70px_rgba(16,50,74,0.12)] backdrop-blur-sm"></div>
            <div class="relative overflow-hidden rounded-[2rem] bg-[#f0ede6] shadow-[0_20px_70px_rgba(16,50,74,0.12)] ring-1 ring-black/5">
              <div class="grid gap-6 p-6 sm:p-8">
                <div class="overflow-hidden rounded-[1.75rem] bg-gradient-to-br from-[#dce8e2] via-[#efe9de] to-[#d9e1ea]">
                  <div class="grid min-h-[22rem] gap-0 lg:grid-cols-5">
                    <div class="flex flex-col justify-between p-6 lg:col-span-3 lg:p-8">
                      <div>
                        <div class="inline-flex items-center gap-2 rounded-full bg-white/80 px-3 py-1 text-xs font-medium text-slate-600">
                          <MoonStar size={14} />
                          A calmer path to care
                        </div>
                        <h2 class="mt-4 max-w-md text-3xl font-semibold tracking-tight text-[#12222f]">
                          Support that feels personal, structured, and grounded
                        </h2>
                        <p class="mt-3 max-w-md text-sm leading-6 text-slate-600">
                          From screening to ongoing treatment, the experience is designed to keep every step understandable.
                        </p>
                      </div>

                      <div class="grid gap-3 sm:grid-cols-2">
                        <div class="rounded-3xl bg-white/80 p-4 backdrop-blur">
                          <div class="flex items-center gap-3">
                            <div class="flex h-10 w-10 items-center justify-center rounded-2xl bg-[#10324a] text-white">
                              <CircleCheckBig size={16} />
                            </div>
                            <div>
                              <div class="text-sm font-semibold">Integrated care</div>
                              <div class="text-xs text-slate-500">Therapy, psychiatry, and support</div>
                            </div>
                          </div>
                        </div>
                        <div class="rounded-3xl bg-white/80 p-4 backdrop-blur">
                          <div class="flex items-center gap-3">
                            <div class="flex h-10 w-10 items-center justify-center rounded-2xl bg-[#10324a] text-white">
                              <MapPinned size={16} />
                            </div>
                            <div>
                              <div class="text-sm font-semibold">Centres available</div>
                              <div class="text-xs text-slate-500">Bengaluru, Mumbai, New Delhi</div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>

                    <div class="relative flex items-end justify-center bg-white/35 p-4 lg:col-span-2">
                      <div class="relative h-[19rem] w-full max-w-[14rem] rounded-[2rem] bg-[#10324a] p-4 text-white shadow-2xl">
                        <div class="absolute left-1/2 top-4 h-1 w-12 -translate-x-1/2 rounded-full bg-white/30"></div>
                        <div class="mt-8 rounded-[1.6rem] bg-white/10 p-4 backdrop-blur">
                          <div class="flex items-center justify-between">
                            <div class="text-xs uppercase tracking-[0.2em] text-white/70">Today</div>
                            <ShieldCheck size={16} class="text-white/70" />
                          </div>
                          <div class="mt-3 text-lg font-semibold">Your care journey</div>
                          <div class="mt-3 space-y-3">
                            <div class="flex items-center gap-3 rounded-2xl bg-white/10 px-3 py-2">
                              <div class="flex h-8 w-8 items-center justify-center rounded-xl bg-white text-[#10324a]">
                                <ClipboardList size={15} />
                              </div>
                              <div class="text-sm">Assessment</div>
                            </div>
                            <div class="flex items-center gap-3 rounded-2xl bg-white/10 px-3 py-2">
                              <div class="flex h-8 w-8 items-center justify-center rounded-xl bg-white text-[#10324a]">
                                <MessageSquareHeart size={15} />
                              </div>
                              <div class="text-sm">Consultation</div>
                            </div>
                            <div class="flex items-center gap-3 rounded-2xl bg-white/10 px-3 py-2">
                              <div class="flex h-8 w-8 items-center justify-center rounded-xl bg-white text-[#10324a]">
                                <CheckCircle2 size={15} />
                              </div>
                              <div class="text-sm">Ongoing support</div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>

                <div class="grid gap-3 sm:grid-cols-3">
                  {#each trustBadges as badge}
                    <div class="rounded-3xl bg-white p-4 shadow-sm ring-1 ring-black/5">
                      <div class="text-sm font-semibold text-[#10324a]">{badge.label}</div>
                      <div class="text-xs text-slate-500">{badge.sub}</div>
                    </div>
                  {/each}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="experts" class="mx-auto max-w-7xl px-4 pb-8 sm:px-6 lg:px-8">
      <div class="grid gap-6 lg:grid-cols-12">
        <div class="lg:col-span-4">
          <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
            <div class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold uppercase tracking-[0.22em] text-[#10324a]">
              Experts
            </div>
            <h2 class="mt-4 text-2xl font-semibold tracking-tight">Choose the right specialist for the concern at hand.</h2>
            <p class="mt-3 text-sm leading-7 text-slate-600">
              A clear path to therapists, psychiatrists, child and youth experts, and couples therapists.
            </p>
            <a href="#contact" class="mt-5 inline-flex items-center gap-2 text-sm font-semibold text-[#10324a]">
              Start a conversation <ArrowRight size={16} />
            </a>
          </div>
        </div>

        <div class="lg:col-span-8">
          <div class="grid gap-4 md:grid-cols-2">
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <Users size={20} />
                </div>
                <div>
                  <div class="font-semibold">Therapists</div>
                  <div class="text-sm text-slate-500">Supportive, structured sessions</div>
                </div>
              </div>
            </div>
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <Stethoscope size={20} />
                </div>
                <div>
                  <div class="font-semibold">Psychiatrists</div>
                  <div class="text-sm text-slate-500">Clinical evaluation and medication support</div>
                </div>
              </div>
            </div>
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <Sparkles size={20} />
                </div>
                <div>
                  <div class="font-semibold">Child and Youth Experts</div>
                  <div class="text-sm text-slate-500">Developmentally informed care</div>
                </div>
              </div>
            </div>
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <Users size={20} />
                </div>
                <div>
                  <div class="font-semibold">Couples Therapists</div>
                  <div class="text-sm text-slate-500">Repair, clarity, and shared goals</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="services" class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
      <div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
        <div>
          <div class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold uppercase tracking-[0.22em] text-[#10324a] shadow-sm ring-1 ring-black/5">
            Services
          </div>
          <h2 class="mt-4 text-3xl font-semibold tracking-tight">A comprehensive set of care pathways.</h2>
        </div>
        <p class="max-w-2xl text-sm leading-7 text-slate-600">
          Move from screening to treatment and follow-up without losing continuity across teams or modalities.
        </p>
      </div>

      <div class="mt-8 grid gap-4 md:grid-cols-2 xl:grid-cols-3">
        {#each services as service}
          <article class="group rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 transition hover:-translate-y-0.5 hover:shadow-md">
            <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#10324a] text-white shadow-sm">
              <svelte:component this={service.icon} size={20} />
            </div>
            <h3 class="mt-5 text-xl font-semibold tracking-tight">{service.title}</h3>
            <p class="mt-3 text-sm leading-7 text-slate-600">{service.desc}</p>
            <div class="mt-5 inline-flex items-center gap-2 text-sm font-semibold text-[#10324a]">
              Learn more <ChevronRight size={16} class="transition group-hover:translate-x-0.5" />
            </div>
          </article>
        {/each}
      </div>
    </section>

    <section id="centres" class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
      <div class="grid gap-6 lg:grid-cols-12">
        <div class="lg:col-span-5">
          <div class="rounded-[2rem] bg-[#10324a] p-8 text-white shadow-lg">
            <div class="inline-flex items-center gap-2 rounded-full bg-white/10 px-3 py-1 text-xs font-semibold uppercase tracking-[0.22em] text-white/80">
              Centres
            </div>
            <h2 class="mt-4 text-3xl font-semibold tracking-tight">In-person care where it matters.</h2>
            <p class="mt-3 text-sm leading-7 text-white/80">
              Centres in Bengaluru, Mumbai, and New Delhi keep the experience human, local, and accessible.
            </p>
            <div class="mt-6 grid gap-3 sm:grid-cols-3">
              <div class="rounded-3xl bg-white/10 p-4">
                <div class="text-sm font-semibold">Bengaluru</div>
                <div class="text-xs text-white/70">Clinic centre</div>
              </div>
              <div class="rounded-3xl bg-white/10 p-4">
                <div class="text-sm font-semibold">Mumbai</div>
                <div class="text-xs text-white/70">Clinic centre</div>
              </div>
              <div class="rounded-3xl bg-white/10 p-4">
                <div class="text-sm font-semibold">New Delhi</div>
                <div class="text-xs text-white/70">Clinic centre</div>
              </div>
            </div>
          </div>
        </div>

        <div class="lg:col-span-7">
          <div class="grid gap-4 md:grid-cols-2">
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <MapPinned size={20} />
                </div>
                <div>
                  <div class="font-semibold">Local access</div>
                  <div class="text-sm text-slate-500">Clinic appointments and referrals</div>
                </div>
              </div>
            </div>
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center gap-3">
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#eaf1f4] text-[#10324a]">
                  <Phone size={20} />
                </div>
                <div>
                  <div class="font-semibold">Reach out anytime</div>
                  <div class="text-sm text-slate-500">Support for questions and next steps</div>
                </div>
              </div>
            </div>
            <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 md:col-span-2">
              <div class="flex flex-col justify-between gap-6 md:flex-row md:items-center">
                <div>
                  <div class="text-sm font-semibold uppercase tracking-[0.22em] text-[#10324a]">Contact</div>
                  <h3 id="contact" class="mt-2 text-2xl font-semibold tracking-tight">Need help deciding where to start?</h3>
                  <p class="mt-2 max-w-2xl text-sm leading-7 text-slate-600">
                    The homepage funnels users toward the right expert, while keeping the broader organisation visible.
                  </p>
                </div>
                <div class="flex flex-col gap-3 sm:flex-row">
                  <a
                    href="mailto:hello@example.com"
                    class="inline-flex items-center justify-center gap-2 rounded-full border border-slate-300 bg-white px-5 py-3 text-sm font-semibold text-slate-700 transition hover:border-[#10324a] hover:text-[#10324a]"
                  >
                    Email support
                  </a>
                  <a
                    href="#"
                    class="inline-flex items-center justify-center gap-2 rounded-full bg-[#10324a] px-5 py-3 text-sm font-semibold text-white shadow-sm"
                  >
                    Call now <ArrowRight size={16} />
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="resources" class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
      <div class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5 sm:p-8">
        <div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
          <div>
            <div class="inline-flex items-center gap-2 rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold uppercase tracking-[0.22em] text-[#10324a]">
              Resources
            </div>
            <h2 class="mt-4 text-3xl font-semibold tracking-tight">Guided content, assessments, and support kits.</h2>
          </div>
          <p class="max-w-2xl text-sm leading-7 text-slate-600">
            The public homepage keeps a library-style section close to the top of the information hierarchy.
          </p>
        </div>

        <div class="mt-6 flex flex-wrap gap-3">
          {#each resources as resource}
            <span class="rounded-full border border-slate-200 bg-slate-50 px-4 py-2 text-sm font-medium text-slate-700">
              {resource}
            </span>
          {/each}
        </div>
      </div>
    </section>

    <section id="conditions" class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
      <div class="flex flex-col gap-4 md:flex-row md:items-end md:justify-between">
        <div>
          <div class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold uppercase tracking-[0.22em] text-[#10324a] shadow-sm ring-1 ring-black/5">
            Conditions
          </div>
          <h2 class="mt-4 text-3xl font-semibold tracking-tight">Common care areas, grouped clearly.</h2>
        </div>
        <p class="max-w-2xl text-sm leading-7 text-slate-600">
          A visible conditions section helps visitors self-identify quickly and move to the right service path.
        </p>
      </div>

      <div class="mt-8 grid gap-4 md:grid-cols-2 xl:grid-cols-3">
        {#each conditions as item}
          <article class="rounded-[2rem] bg-white p-6 shadow-sm ring-1 ring-black/5">
            <div class="inline-flex rounded-full bg-[#eef4f1] px-3 py-1 text-xs font-semibold uppercase tracking-[0.2em] text-[#10324a]">
              {item.tag}
            </div>
            <h3 class="mt-4 text-xl font-semibold tracking-tight">{item.title}</h3>
            <p class="mt-3 text-sm leading-7 text-slate-600">{item.desc}</p>
          </article>
        {/each}
      </div>
    </section>

    <section class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
      <div class="rounded-[2rem] bg-[#edf2f4] p-6 sm:p-8">
        <div class="grid gap-8 lg:grid-cols-12 lg:items-center">
          <div class="lg:col-span-7">
            <div class="inline-flex items-center gap-2 rounded-full bg-white px-3 py-1 text-xs font-semibold uppercase tracking-[0.22em] text-[#10324a] shadow-sm ring-1 ring-black/5">
              App
            </div>
            <h2 class="mt-4 text-3xl font-semibold tracking-tight text-[#12222f]">Keep the next step within reach.</h2>
            <p class="mt-3 max-w-2xl text-sm leading-7 text-slate-600">
              The original page promotes the app and trust markers in the footer area; this version mirrors that
              layout pattern with an accessible CTA block.
            </p>
          </div>
          <div class="lg:col-span-5">
            <div class="rounded-[2rem] bg-white p-5 shadow-sm ring-1 ring-black/5">
              <div class="flex items-center justify-between gap-4">
                <div>
                  <div class="text-sm font-semibold">Download the app</div>
                  <div class="text-xs text-slate-500">Simplify booking and follow-up</div>
                </div>
                <div class="flex h-12 w-12 items-center justify-center rounded-2xl bg-[#10324a] text-white">
                  <Phone size={18} />
                </div>
              </div>
              <div class="mt-4 flex items-center gap-3">
                <button class="inline-flex items-center gap-2 rounded-full bg-[#10324a] px-5 py-3 text-sm font-semibold text-white">
                  App Store <ArrowRight size={16} />
                </button>
                <button class="inline-flex items-center gap-2 rounded-full border border-slate-300 px-5 py-3 text-sm font-semibold text-slate-700">
                  Learn more
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer class="border-t border-black/5 bg-white">
    <div class="mx-auto max-w-7xl px-4 py-10 sm:px-6 lg:px-8">
      <div class="grid gap-10 lg:grid-cols-12">
        <div class="lg:col-span-4">
          <div class="flex items-center gap-3">
            <div class="flex h-11 w-11 items-center justify-center rounded-2xl bg-[#10324a] text-white">
              <MessageSquareHeart size={20} />
            </div>
            <div>
              <div class="font-semibold">Amaha</div>
              <div class="text-sm text-slate-500">© 2026</div>
            </div>
          </div>
          <p class="mt-4 max-w-md text-sm leading-7 text-slate-600">
            This is an original SvelteKit implementation inspired by the structure and tone of the public homepage.
          </p>
        </div>

        <div class="lg:col-span-8">
          <div class="grid gap-8 sm:grid-cols-2 xl:grid-cols-4">
            {#each navGroups as group}
              <div>
                <h3 class="text-sm font-semibold text-slate-900">{group.title}</h3>
                <ul class="mt-4 space-y-3">
                  {#each group.items as item}
                    <li>
                      <a href={item.href} class="text-sm text-slate-600 transition hover:text-[#10324a]">{item.label}</a>
                    </li>
                  {/each}
                </ul>
              </div>
            {/each}
          </div>
        </div>
      </div>

      <div class="mt-10 flex flex-col gap-4 border-t border-slate-200 pt-6 text-sm text-slate-500 sm:flex-row sm:items-center sm:justify-between">
        <div class="flex flex-wrap gap-x-4 gap-y-2">
          <a href="#" class="transition hover:text-[#10324a]">Privacy Policy</a>
          <a href="#" class="transition hover:text-[#10324a]">Terms &amp; Conditions</a>
          <a href="#" class="transition hover:text-[#10324a]">Sitemap</a>
          <a href="#" class="transition hover:text-[#10324a]">Hall of Fame</a>
        </div>
        <div class="max-w-2xl text-sm leading-7 text-slate-500">
          For urgent safety concerns or life-threatening situations, contact local emergency services or a crisis helpline.
        </div>
      </div>
    </div>
  </footer>
</div>
