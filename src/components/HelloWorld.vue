<template>
  <DocumentEditor
    id="docEditor"
    :documentServerUrl="docServerUrl"
    :config="config"
    :events_onDocumentReady="onDocumentReady"
  />
</template>

<script>
// import { DocumentEditor1 } from '@onlyoffice/document-editor-vue';
import DocumentEditor from './DocEditor.vue';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: { DocumentEditor },
  data() {
    return {
      docServerUrl: 'http://192.168.0.192:9000/',
      config: {
        width: 1200,
        height: 800,
        // token: '',
        document: {
          fileType: 'docx',
          // key: '%E5%8B%98%E6%8E%A2%E8%AF%84%E4%BB%B7%E9%A1%B5%E9%9D%A2.docx',
          // permissions: {
          //   comment: true,
          //   commentGroups: {
          //     edit: ['Group2', ''],
          //     remove: [''],
          //     view: ''
          //   },
          //   copy: true,
          //   deleteCommentAuthorOnly: false,
          //   download: true,
          //   edit: true,
          //   editCommentAuthorOnly: false,
          //   fillForms: true,
          //   modifyContentControl: true,
          //   modifyFilter: true,
          //   print: true,
          //   review: true,
          //   reviewGroups: ['Group1', 'Group2', '']
          // },
          // title: '针对矿方提出的三个要求.docx',
          // url: 'http://192.168.0.192:9000/example/download?fileName=%E5%8B%98%E6%8E%A2%E8%AF%84%E4%BB%B7%E9%A1%B5%E9%9D%A2.docx'
          // url: 'http://192.168.0.192:9000/dictionaries/%E5%8B%98%E6%8E%A2%E8%AF%84%E4%BB%B7%E9%A1%B5%E9%9D%A2.docx'
          // url: 'http://192.168.0.192:9000/static/%E5%8B%98%E6%8E%A2%E8%AF%84%E4%BB%B7%E9%A1%B5%E9%9D%A2.docx'
          // key: 'test1.docx',
          // title: 'test1.docx',
          // url: `http://192.168.0.192:3000/static/test1.docx`
          key: '勘探评价页面.docx',
          title: '勘探评价页面.docx',
          url:"http://192.168.8.7:9000/common/勘探评价页面.docx"
          // url: `http://192.168.8.7:49676/api/v1/buckets/common/objects/download?prefix=5YuY5o6i6K+E5Lu36aG16Z2iLmRvY3g=&version_id=null`
        },
        documentType: 'word',
        editorConfig: {
          callbackUrl: 'http://192.168.0.192:9000/api/v1/onlyoffice/callback',
          lang: 'zh-CN',
          user: { group: '技术', id: 'wfd', name: 'John Smith' }
          // coEditing: {
          //   mode: 'fast',
          //   change: true
          // },
          // mode: 'view'
        }
      }
    };
  },
  methods: {
    onDocumentReady() {
      console.log('Document is loaded');
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
