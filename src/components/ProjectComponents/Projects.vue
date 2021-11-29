<template>
            <div class="project-container">
                <a target="_blank" class='git-link' :href="gitAccount">{{this.gitAccount}}</a>
                <img class="git-icon" src="@/assets/git.svg" alt="git icon">
                <ul class="github-projects">
                    <project v-for="proj in githubProjects" :key="proj.name" :project="proj">
                    </project>
                </ul>
            </div>
</template>
<script>
import Project from './Project.vue';

export default {
    created() {
        fetch('https://api.github.com/users/Zack-Contreras/repos')
        .then(response => response.json())
        .then((data) => {
            console.log(data)
            this.githubProjects = data.map((p) => {
                return {...p, open_accordian:false};
            });
        });
    },
    name: 'Projects',
    components: {
        'project': Project,
    },
    data() {
        return {
            githubProjects: [],
            gitAccount: "https://github.com/Zack-Contreras"
        }
    }
}
</script>

<style scoped>
.project-container {
    display: flex;
    height: 100%;
    justify-content: flex-end;
    flex-direction: column;
    padding: .5rem;
}

.git-link {
    font-size: 2rem;
    color: darkcyan;
}

.git-icon{
    height: 12rem;
    padding: 2rem;
}

.github-projects {
    height: auto;
    max-height: 30rem;
    width: 80%;
    overflow-y: scroll;
    margin: auto;
    margin-top: 0;
    margin-bottom: 0;
    list-style: none;
}
</style>