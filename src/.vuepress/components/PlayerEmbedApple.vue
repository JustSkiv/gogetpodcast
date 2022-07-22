<template>
  <span>
   <iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" height="175"
           style="width:100%;max-width:660px;overflow:hidden;background:transparent;border: 0;"
           sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation"
           :src=embedSrc></iframe>

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
      return "https://embed.podcasts.apple.com/us/podcast/" + this.authorId+ "?i=" + this.episodeId;
    },
    link() {
      return "https://podcasts.apple.com/us/podcast/" + this.authorId + "?i=" + this.episodeId;
    },
    authorLink() {
      return "https://podcasts.apple.com/us/podcast/go-get-podcast/" + this.authorId;
    },
  },
}
</script>