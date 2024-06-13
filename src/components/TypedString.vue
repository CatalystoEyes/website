<template>
  <div>
    <div id="typed-strings">
      <p class="text-center">I'm <strong>Software Engineer</strong></p>
      <p class="text-center">
        I'm <em>working</em> with
        <strong>React, Vue, Next.js, Node.js and other tools.</strong>
      </p>
    </div>
    <div class="text-center mt-6">
      <span ref="typedElement"></span>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from "vue";
import Typed from "typed.js";

const defaultOptions = {
  strings: [
    "These are the default values...",
    "You know what you should do?",
    "Use your own!",
    "Have a great day!",
  ],
  typeSpeed: 40,
  loop: true,
  cursorChar: "|",
  showCursor: true,
  backSpeed: 25,
  backDelay: 700,
  startDelay: 300,
  shuffle: false,
};

export default {
  name: "TypedString",
  setup() {
    const typedElement = ref(null);
    let typed = null;

    onMounted(() => {
      const options = {
        stringsElement: "#typed-strings",
        ...defaultOptions,
      };
      typed = new Typed(typedElement.value, options);
    });

    return {
      typedElement,
    };
  },
};
</script>
