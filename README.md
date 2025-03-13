const works = {
    "task1": { "title": "Project 1", "url": "works/task1/index.html", "color": "red" },
    "task2": { "title": "Project 2", "url": "works/task2/index.html", "color": "green" },
    "task3": { "title": "Project 3", "url": "works/task3/index.html", "color": "darkblue" },
};

const workList = document.getElementById("workList");
const workTitle = document.getElementById("workTitle");
const projectFrame = document.getElementById("projectFrame");
const content = document.querySelector(".content");

// Populate the sidebar with work titles
for (const key in works) {
    let li = document.createElement("li");
    li.textContent = works[key].title;
    li.onclick = function () {
        loadProject(key);
    };
    workList.appendChild(li);
}

function loadProject(task) {
    workTitle.textContent = works[task].title;
    projectFrame.src = works[task].url;
    projectFrame.style.display = "block";
    document.body.style.backgroundColor = works[task].color;
    content.style.opacity = "1";
    projectFrame.style.transform = "scale(1)";
    projectFrame.style.opacity = "1";
}
