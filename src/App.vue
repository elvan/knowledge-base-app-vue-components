<template>
  <div>
    <active-element
      :topic-title="activeTopic && activeTopic.title"
      :text="activeTopic && activeTopic.fullText"
    ></active-element>
    <knowledge-base
      :topics="topics"
      @select-topic="activateTopic"
    ></knowledge-base>
  </div>
</template>

<script>
export default {
  data() {
    return {
      topics: [
        {
          id: 'basics',
          title: 'The Basics',
          description: 'Core Vue basics you have to know',
          fullText:
            'Vue is a great framework and it has a couple of key concepts: Data binding, events, components and reactivity - that should tell you something!',
        },
        {
          id: 'components',
          title: 'Components',
          description:
            'Components are a core concept for building Vue UIs and apps',
          fullText:
            'With components, you can split logic (and markup) into separate building blocks and then combine those building blocks (and re-use them) to build powerful user interfaces.',
        },
      ],
      activeTopic: null,
    };
  },
  methods: {
    activateTopic(topicId) {
      this.activeTopic = this.topics.find((topic) => topic.id === topicId);
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
html {
  font-family: sans-serif;
}
body {
  margin: 0;
}
section {
  max-width: 40rem;
  margin: 2rem auto;
  padding: 1rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}

ul {
  display: flex;
  justify-content: center;
  margin: 0;
  padding: 0;
  list-style: none;
}

li {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 15rem;
  margin: 0 1rem;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 12px;
}

h2 {
  margin: 0.75rem 0;
  text-align: center;
}

button {
  padding: 0.75rem 2rem;
  border: 1px solid #c70053;
  border-radius: 30px;
  color: white;
  font: inherit;
  cursor: pointer;
  background-color: #c70053;
}

button:hover,
button:active {
  border-color: #e24d8b;
  background-color: #e24d8b;
}
</style>
