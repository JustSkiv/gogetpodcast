<template>
  <span>
    <iframe style="border-radius:12px;border: 0;" :src=embedSrc width="100%" height="232"
            allowfullscreen=""
            allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>

     <div style="font-size: 10px;
      color: #cccccc;
      line-break: anywhere;word-break: normal;
      overflow: hidden;white-space: nowrap;
      text-overflow: ellipsis;
       font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;
       font-weight: 100;">

    <a :href=authorLink :title=author target="_blank"
       style="color: #cccccc; text-decoration: none;">{{ author }}</a> · <a
         :href=link
         :title=title
         style="color: #cccccc; text-decoration: none;">{{ title }}</a></div>
  </span>
</template>

<script>
export default {
  props: {
    title: String,
    author: String,
    authorId: String,
    src: String,
    episodeId: String,
  },
  data() {
    return {
      // title: 'title is missed'
    }
  },
  computed: {
    embedSrc() {
      return "https://open.spotify.com/embed/episode/" + this.episodeId;
    },
    link() {
      return "https://open.spotify.com/episode/" + this.episodeId;
    },
    authorLink() {
      return "https://open.spotify.com/show/" + this.authorId;
    },
  },
}
</script>