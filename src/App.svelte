<script lang="ts">
  import gitHubLogo from "./assets/github-svgrepo-com.svg";
  import linkedIn from "./assets/linkedin-svgrepo-com.svg";
  import massenaImg from "./assets/Massena.png";
  import n7Img from "./assets/n7.png";
  import aaacnesImg from "./assets/projects/3acnes.png";
  import jeuTrain from "./assets/projects/jeuTrain.png";
  import mobiliteImg from "./assets/projects/plateformeMobilites.png";
  import vdconnectImg from "./assets/projects/vdconnect_logo.png";
  import tlsSec from "./assets/tls-sec.jpeg";
  import Button from "./lib/Button.svelte";
  import Tags from "./lib/Tags.svelte";

  interface Project {
    name: string;
    description: string;
    year: number;
    image: string;
    shadow: boolean;
    techno: string[];
  }

  interface School {
    name: string;
    description: string;
    year: string;
    image: [string, string];
  }

  let projects = [
    {
      name: "Plateforme de gestion des mobilités",
      description:
        "Mobility management platform for university. Realized in group for a N7 project. I took care of the frontend and a bit of the backend.",
      year: 2022,
      image: mobiliteImg,
      shadow: true,
      techno: ["Java", "React", "Tailwind CSS"],
    },
    {
      name: "VDConnect",
      description:
        "Mobile application for the Toulouse Vaccination Centre, developed as part of my summer work in 2021 with 5 others people. It is used to clock in/out staff, send them notifications, provide a clocking history and forecast the number of meals to be ordered.",
      year: 2021,
      image: vdconnectImg,
      shadow: true,
      techno: ["Flutter", "Firebase", "Javascript"],
    },
    {
      name: "3Acnes website",
      description:
        "Website created for an association (3Acnes) with N7Consulting. Content management system, membership, subscription, events.",
      year: 2021,
      image: aaacnesImg,
      shadow: true,
      techno: ["PHP", "SQL", "HTML", "CSS", "Bootstrap", "Javascript"],
    },
    {
      name: "Train management simulation",
      description:
        "I developed this game with my group for a project in the Object Technology course. The goal was to create a railway traffic simulation game. The player has to create lines, buy trains and position them in such a way that a station is not completely filled with passengers.",
      year: 2021,
      image: jeuTrain,
      shadow: false,
      techno: ["Java (Swing for UI)"],
    },
  ];

  let schools = [
    {
      name: "TLS-SEC",
      description: "ENSEEIHT x INSA Toulouse",
      year: "2022 - 2023",
      image: tlsSec,
    },
    {
      name: "ENSEEIHT",
      description: "Science du numérique",
      year: "2020 - 2023",
      image: n7Img,
    },
    {
      name: "Lycée Masséna",
      description: "Classe Préparatoire MPSI - PSI",
      year: "2018 - 2020",
      image: massenaImg,
    },
    {
      name: "Lycée Raynouard",
      description:
        "Baccalauréat Scientifique - Mention Très Bien section Européenne Anglais",
      year: "2018",
      image: "",
    },
  ];
</script>

<main
  class="antialiased h-screen w-screen background snap-proximity snap-y dark:text-white"
>
  <div class="grid min-h-screen place-items-center snap-center">
    <div />
    <div class="grid place-items-center">
      <h1 class="text-6xl font-semibold font-mono pb-4">Justin Facquet</h1>
      <p class="text-sm">
        M2 student, Digital Sciences and Engineering, Cybersecurity, <a
          class="underline decoration-wavy underline-offset-2 decoration-red-900 dark:decoration-white"
          href="https://www.enseeiht.fr/"
          target="_blank">INP-ENSEEIHT</a
        >.
      </p>
      <p class="text-sm">France</p>

      <div class="flex">
        <a href="https://github.com/JustinF18" target="_blank">
          <img
            src={gitHubLogo}
            class="h-24 p-6 hover:drop-shadow-xl"
            alt="GitHub Logo"
          />
        </a>
        <a
          href="https://www.linkedin.com/in/justin-facquet-8a99471aa/"
          target="_blank"
        >
          <img
            src={linkedIn}
            class="h-24 p-6 hover:drop-shadow-xl"
            alt="Svelte Logo"
          />
        </a>
      </div>
    </div>
    <div>
      <div>
        <Button text="Technical Projects" url="#projects-overview" logo="💻" />
        <Button text="Education" url="#education" logo="🎓" />
      </div>
      <div class="grid place-items-center mt-10">
        <div class="animate-bounce p-2 w-10 h-10">
          <svg
            class="w-6 h-6 text-blue-900"
            fill="none"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path d="M19 14l-7 7m0 0l-7-7m7 7V3" />
          </svg>
        </div>
      </div>
    </div>
  </div>
  <div
    class="min-h-screen grid place-items-center snap-center w-full py-24 dark:bg-slate-800"
    id="projects-overview"
  >
    <div class="text-center w-full">
      <h2 class="text-2xl font-semibold font-mono pb-24">
        💻 Technical Projects
      </h2>
      <div class="overflow-hidden ">
        <div class="max-w-full flex gap-6 snap-x overflow-x-auto pb-14">
          {#each projects as project}
            <div class="flex-none snap-normal snap-center first:pl-8 last:pr-8">
              <div class="flex flex-col items-center justify-center gap-3">
                <img
                  class="h-52 object-cover {project.shadow
                    ? 'shadow-2xl rounded-xl'
                    : ''}"
                  src={project.image}
                  alt={project.name}
                />
                <div class="p-4">
                  <h5 class="text-xl font-bold text-gray-900 dark:text-white">
                    {project.name}
                  </h5>
                  <p class="mt-2 text-gray-500 max-w-xs dark:text-gray-100">
                    {project.description}
                  </p>
                  <div class="flex flex-wrap mt-2 max-w-xs justify-center">
                    {#each project.techno as techno}
                      <Tags text={techno} />
                    {/each}
                  </div>
                </div>
              </div>
            </div>
          {/each}
        </div>
      </div>
    </div>
  </div>
  <div
    class="min-h-screen grid place-items-center snap-center bg-gray-100 py-24 dark:bg-slate-800"
    id="education"
  >
    <h2 class="text-2xl font-semibold font-mono mb-12">🎓 Education</h2>
    <div class="container mx-auto w-full h-full">
      <div class="relative wrap overflow-hidden h-full">
        <div
          class="absolute left-1/2 border-opacity-20 border-gray-600 h-full border"
        />
        {#each schools as school}
          <div
            class="mb-8 flex odd:flex-row-reverse justify-between items-center w-full"
          >
            <div class="order-1 w-5/12" />
            <div
              class="z-20 flex items-center order-1 bg-blue-900 shadow-xl w-32 h-8 rounded-full"
            >
              <h1 class="mx-auto font-semibold text-lg text-white">
                {school.year}
              </h1>
            </div>
            <div
              class="order-1 flex flex-col lg:flex-row items-center justify-center gap-3 w-5/12 px-6 py-4"
            >
              {#if school.image != ""}
                <img
                  class="h-24 object-cover shadow-xl rounded-xl"
                  src={school.image}
                  alt={school.name}
                />
              {/if}
              <div class="p-4">
                <h5 class="text-xl font-bold text-gray-900 dark:text-white">
                  {school.name}
                </h5>
                <p class="mt-2 text-gray-500 max-w-xs dark:text-white">
                  {school.description}
                </p>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</main>
