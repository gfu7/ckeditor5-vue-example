<template>
  <div id="app">
    <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
  </div>
</template>

<script lang="ts">
// ⚠️ NOTE: We don't use @ckeditor/ckeditor5-build-classic any more!
// Since we're building CKEditor 5 from source, we use the source version of ClassicEditor.
import { ClassicEditor } from '@ckeditor/ckeditor5-editor-classic';
import { Essentials } from '@ckeditor/ckeditor5-essentials';
import { Paragraph } from '@ckeditor/ckeditor5-paragraph';

export default {
  name: 'app',
  data() {
    return {
      editor: ClassicEditor,
      editorData: '<p>Content of the editor.</p>',
      editorConfig: {
        plugins: [
          Essentials,
          Paragraph
        ],

        toolbar: {
          items: [
            'undo',
            'redo'
          ]
        }
      }
    };
  }
};
</script>
