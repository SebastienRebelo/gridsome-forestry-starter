<template>
    <div class="projects">
        <div class="project" v-for="item in projects" :key="item.node.id">
            <g-link :to="item.node.path" class="project-link">

            <h3 class="project-title">{{ item.node.title }}</h3>
            <div class="categories">
                <span class="category" v-for="(item, index) in item.node.categories" :key="index">{{ item }}</span>
            </div>
            </g-link>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        projects: {
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>
.project
{
  margin-top: 100px;
}
.project:hover
{
  margin-left: 6%;
  transition-duration: 500ms;
}
.project-link {
  text-decoration: none;
}
.thumbnail {
  height: 560px;
  object-fit: cover;
  transition: all 0.15s ease;
  box-shadow: 0 0 40px -20px rgba(0,0,0,0.25);
}
.project-title {
  font-size: 4rem;
  color: var(--color-contrast);
  margin: 2rem 0 1rem 0;
}
.categories {
  font-size: 0.8rem;
  color: var(--color-contrast-1);

}
.category {
  margin-right: 0.8rem;
  color: #ffcc32;
}
.category:last-of-type {
  margin: 0;
}
.project:hover .thumbnail {
  transform: scale(1.02);
  box-shadow: 0 20px 40px -20px rgba(0,0,0,0.25);
}

@media (min-width: 920px) {
  .project {
    grid-column: auto / span 1;
  }
  .project:nth-child(3n+1) {
    grid-column: auto / span 2;
  }
}

</style>
