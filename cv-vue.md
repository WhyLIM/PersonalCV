<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/element-plus/dist/index.css" />
  <script src="https://cdn.jsdelivr.net/npm/vue@3"></script>
  <script src="https://cdn.jsdelivr.net/npm/element-plus"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <link href="./fa/css/fontawesome.css" rel="stylesheet">
  <link href="./fa/css/brands.css" rel="stylesheet">
  <link href="./fa/css/solid.css" rel="stylesheet">
  <link href="./fa/css/regular.css" rel="stylesheet">
</head>

<center>
     <h1>Min Li (李旻)</h1>
     <div>
         <span>
             <i class="fa-solid fa-phone"></i>
             +86 18851387887
         </span>
         ·
         <span>
             <i class="fa-solid fa-envelope"></i>
             lim@gdph.org.cn
         </span>
         ·
         <span>
             <i class="fa-brands fa-github"></i>
             <a href="https://github.com/WhyLIM">WhyLIM</a>
         </span>
         ·
         <span>
             <i class="fa-brands fa-chrome"></i>
             <a href="cv.limina.top">CV</a>
         </span>
     </div>
 </center>

## <i class="fa-solid fa-graduation-cap"></i> EDUCATION

-   Bachelor of Sciences in Bioinformatics, **Soochow University**, China (Sep 2018 - Jun 2022)

## <i class="fa-solid fa-address-card"></i> EMPLOYMENT

-   **Research Assistant**
    Medical Research Institute, Guangdong Provincial People's Hospital (Guangdong Academy of Medical Sciences), Southern Medical University, Guangzhou, China (Mar 2023 - present)

## <i class="fa-solid fa-chart-column"></i> SKILLS

<div id="app">
    <div class="content-container">
        <div class="charts-container">
            <canvas id="skillsChart"></canvas>
        </div>
        <div class="skills-container">
            <div class="skill" v-for="skill in skills" :key="skill.name">
                <div class="skill-name">
                    <i :class="['skill-icon', skill.icon]"></i>
                    {{ skill.name }}
                </div>
                <el-progress :percentage="skill.level" :color="skill.color" :show-text="false"></el-progress>
            </div>
        </div>
    </div>
</div>

<script>
    const { createApp } = Vue;
    createApp({
        data() {
            return {
                skills: [
                    { name: "Python", level: 85, icon: "fa-brands fa-python", color: "#5A8693" },
                    { name: "R", level: 90, icon: "fa-solid fa-registered", color: "#D26E3A" },
                    { name: "HTML", level: 70, icon: "fa-brands fa-html5", color: "#EEA23B" },
                    { name: "CSS", level: 65, icon: "fa-brands fa-css3-alt", color: "#D8491D" },
                    { name: "JavaScript", level: 60, icon: "fa-brands fa-js", color: "#855C3E" },
                    { name: "PHP", level: 60, icon: "fa-brands fa-php", color: "#787CB5" },
                    { name: "VUE", level: 70, icon: "fa-brands fa-vuejs", color: "#42b883" },
                    { name: "SQL", level: 65, icon: "fa-solid fa-database", color: "#929BAC" },
                    { name: "Git", level: 50, icon: "fa-brands fa-git-alt", color: "#F05032"},
                    { name: "Shell", level: 70, icon: "fa-brands fa-linux", color: "#172639" },
                ],
                windows: [
                    { name: "Office", level: 90 },
                    { name: "Coding", level: 85 },
                    { name: "Gaming", level: 80 },
                    { name: "Note", level: 75 },
                    { name: "Docker", level: 15 },
                    { name: "Customization", level: 60 }
                ],
                linux: [
                    { name: "Office", level: 20 },
                    { name: "Coding", level: 85 },
                    { name: "Gaming", level: 0 },
                    { name: "Note", level: 70 },
                    { name: "Docker", level: 85 },
                    { name: "Customization", level: 85 }
                ]
            };
        },
        mounted() {
            this.drawSkillsChart();
        },
        methods: {
            drawSkillsChart() {
                const ctx = document.getElementById('skillsChart').getContext('2d');
                const labels = [...new Set([...this.windows.map(task => task.name), ...this.linux.map(task => task.name)])];
                const windowsLevels = labels.map(label => {
                    const task = this.windows.find(task => task.name === label);
                    return task ? task.level : 0;
                });
                const linuxLevels = labels.map(label => {
                    const task = this.linux.find(task => task.name === label);
                    return task ? task.level : 0;
                });
                new Chart(ctx, {
                    type: 'radar',
                    data: {
                        labels: labels,
                        datasets: [{
                            label: 'Windows',
                            data: windowsLevels,
                            fill: true,
                            backgroundColor: 'rgba(0, 120, 214, 0.2)',
                            borderColor: '#0078D6',
                            pointBackgroundColor: '#0078D6',
                            pointBorderColor: '#fff',
                            pointHoverBackgroundColor: '#fff',
                            pointHoverBorderColor: '#0078D6'
                        }, {
                            label: 'Linux',
                            data: linuxLevels,
                            fill: true,
                            backgroundColor: 'rgba(252, 198, 36, 0.2)',
                            borderColor: '#FCC624',
                            pointBackgroundColor: '#FCC624',
                            pointBorderColor: '#fff',
                            pointHoverBackgroundColor: '#fff',
                            pointHoverBorderColor: '#FCC624'
                        }]
                    },
                    options: {
                        elements: {
                            line: {
                                borderWidth: 3
                            }
                        },
                        scale: {
                            ticks: {
                                beginAtZero: true
                            }
                        }
                    }
                });
            }
        }
    }).use(ElementPlus).mount('#app');
</script>

## <i class="fa-brands fa-researchgate"></i> PEER-REVIEWED ARTICLES (Co-first author<sup>#</sup>)

1. Zhang, X.<sup>#</sup>, **Li, M.**<sup>#</sup>, Ye, S.<sup>#</sup>, Shen, K.<sup>#</sup>, Yuan, H., Bakhtyar, S., Peng, Q., Liu, Y., Wang, Y., and Li, M. (2023). CBD2: A functional biomarker database for colorectal cancer. **_iMeta_**, e155. 10.1002/imt2.155.
2. Wang, Z., **Li, M.**, Tang, M., and Hu, G. (2023). From big data to complex network: a navigation through the maze of drug–target interaction. In **_Big Data Analytics in Chemoinformatics and Bioinformatics, (Elsevier)_**, pp. 407-436.

## <i class="fa-solid fa-clipboard-user"></i> CONFERENCE PROCEEDINGS

-   **<u>October 27th-30th, 2023</u>**
    _12th National Conference on Bioinformatics and Systems Biology_, Shandong, China. - **Poster presentation**.

## <i class="fa-solid fa-star"></i> PROFESSIONAL SERVICES

-   Member of Youth Committee of Sichuan Bioinformatics Society (2023-present)

## <i class="fa-solid fa-medal"></i> AWARDS

-   **<u>The 11th place in the Paper Reproduction Challenge of the First BIO-OS Open Source Open Contest - <span style="color: #EA2768;">ByteDance</span>, Dec 2023</u>**
    Successfully collaborated in a team to replicate a complex research paper, **_ranking 11th among 131 participating teams_**.

-   **<u>Second Prize in the 2023 Guangdong Biomedical Big Data Analysis Community Innovation Competition - <span style="color: #EA2768;">Guangdong Bioinformatics Society</span>, Dec 2023</u>**
    Achieved **_Second Prize_** in the 2023 Guangdong Biomedical Big Data Analysis Community Innovation Competition.

-   **<u>Biotechnology Innovation and Practice - <span style="color: #EA2768;">Cold Spring Harbor Asia</span>, Nov 2020</u>**
    For **_successfully completing the project “Biotechnology Innovation and Practice”_** hold by Cold Spring Harbor Asia.

-   **<u>Second Prize in the Huawei ICT Competition 2020 - <span style="color: #EA2768;">HUAWEI</span>, Oct 2020</u>**
    Achieved **_Second Prize_** in the Huawei China University Student ICT Competition 2020 Jiangsu Provincial Preliminary Contest (Undergraduate Cloud Track).

-   **<u>Outstanding Volunteer of Suzhou City - <span style="color: #EA2768;">Suzhou Volunteers Association</span>, Sep 2019</u>**
    Selected as **_“Outstanding Volunteer of Suzhou City”_** during the summer volunteer service event at Suzhou Railway Station in 2019.

<style>
    .content-container {
        display: flex;
        justify-content: space-between;
        align-items: stretch;
    }
    .charts-container {
        padding: 10px;
        float: left;
        width: 38%;
    }
    .skills-container {
        display: flex;
        padding: 10px;
        flex-wrap: wrap;
        justify-content: space-around;
        float: right;
        width: 50%;
    }
    .skill {
        flex-basis: 45%;
        margin-bottom: 3px;
    }
    .skill-icon {
        margin-right: 5px;
    }
    .skill-name {
        display: flex;
        align-items: center;
        margin-bottom: 7px;
    }
</style>
