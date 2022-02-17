<template>
  <span>
    <iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay"
            :src="src"></iframe>

     <div style="font-size: 10px;
      color: #cccccc;
      line-break: anywhere;word-break: normal;
      overflow: hidden;white-space: nowrap;
      text-overflow: ellipsis;
       font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;
       font-weight: 100;">

    <a href="https://soundcloud.com/go-get-podcast" title="Go Get Podcast" target="_blank"
       style="color: #cccccc; text-decoration: none;">{{ author }}</a> · <a
         href="https://soundcloud.com/go-get-podcast/vypusk-1-obsuzhdaem-dzheneriki"
         title="Выпуск 1: Обсуждаем дженерики" target="_blank"
         style="color: #cccccc; text-decoration: none;">{{ title }}</a></div>
  </span>
</template>

<script>
export default {
  props: {
    title: String,
    author: String,
    src: String,
    link: String,
  },
  data() {
    return {
      // title: 'title is missed'
    }
  }
}
</script>