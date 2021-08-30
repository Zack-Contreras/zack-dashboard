<template>
            <div class="project-container">
                <ul class="github-projects">
                    <li v-for="proj in githubProjects" :key="proj.name" class="github-project">
                        {{proj.name}}
                    </li>
                </ul>
            </div>
</template>
<script>
export default {
    created() {
        fetch('https://api.github.com/users/Zack-Contreras/repos')
        .then(response => response.json())
        .then((data) => {
            console.log(data)
            this.githubProjects = data;
        });
    },
    name: 'Projects',
    data() {
        return {
            githubProjects: [],
        }
    }
}
</script>

<style scoped>
.project-container {
    display: flex;
    height: 100%;
    align-items: flex-end;
}

.github-projects {
    height: 25rem;
    width: 80%;
    overflow-y: scroll;
    margin: auto;
    margin-top: 0;
    margin-bottom: 0;
    list-style: none;
}
.github-project {
    width: 100%;
    text-align: start;
    border-radius: 1rem;
    margin: auto;
    margin-bottom: .5rem;
    padding: 1rem;
    cursor: pointer;
    background: rgba(255, 255, 255, 0.4);
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
</style>