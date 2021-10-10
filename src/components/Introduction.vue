<template>
  <section class="intro-container">
    <h1>Designed for the future</h1>

    <div class="images">
      <img
        src="../assets/illustration-editor-mobile.svg"
        alt="editor"
        v-if="isMobile"
      />
      <img
        src="../assets/illustration-editor-desktop.svg"
        alt="editor"
        v-else
      />
    </div>

    <div class="text">
      <article class="article-1">
        <h2>
          Introducing an <br v-if="isMobile" />
          extensible editor
        </h2>

        <p>
          Blogr features an exceedingly intuitive interface which lets you focus
          on one thing: creating content. The editor supports management of
          multiple blogs and allows easy manipulation of embeds such as images,
          videos, and Markdown. Extensibility with plugins and themes provide
          easy ways to add functionality or change the looks of a blog.
        </p>
      </article>

      <article class="article-2">
        <h2>
          Robust content <br v-if="isMobile" />
          management
        </h2>

        <p>
          Flexible content management enables users to easily move through
          posts. Increase the usability of your blog by adding customized
          categories, sections, format, or flow. With this functionality, you’re
          in full control.
        </p>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      isMobile: null,
    };
  },
  methods: {
    checkScreen() {
      if (window.innerWidth > 600) {
        this.isMobile = false;
        return;
      }
      this.isMobile = true;
    },
  },
  created() {
    this.checkScreen();
    window.addEventListener("resize", this.checkScreen);
  },
};
</script>

<style lang="scss" scoped>
.intro-container {
  margin-top: 100px;

  h1 {
    font-size: 1.75rem;
  }
  .images {
    img {
      width: 325px;
    }
  }

  .text {
    article {
      margin: 45px auto;
      width: min(80%, 540px);
      h2 {
        font-size: 1.75rem;
        margin-top: 0;
      }
      p {
        font-size: 1rem;
      }
    }
  }

  @media screen and (min-width: 600px) {
    margin-top: 150px;

    display: grid;
    grid-template-columns: auto auto auto;
    grid-template-areas:
      "heading heading editor"
      "articles articles editor"
      "articles articles editor";
    justify-content: end;
    overflow: hidden;
    h1 {
      //   align-self: center;
      //   justify-self: center;
      grid-area: heading;
      //   align-self: center;
      margin-right: -700px;
    }
    .images {
      margin-right: -240px;
    //   margin-right: 0px;

    //   overflow: hidden;
      grid-area: editor;
    }
    .text {
      grid-area: articles;
      text-align: left;
    }

    .images {
      img {
        width: 885px;
      }
    }
  }
}
</style>