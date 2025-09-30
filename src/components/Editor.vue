<template>
  <ckeditor
      v-model="data"
      :editor="ClassicEditor"
      :config="config"
  />
</template>
<script setup>
import { ref, computed } from 'vue';
import { ClassicEditor, Essentials, Paragraph, Bold, Italic } from 'ckeditor5';
import { FormatPainter } from 'ckeditor5-premium-features';
import { Ckeditor } from '@ckeditor/ckeditor5-vue';

import 'ckeditor5/ckeditor5.css';
import 'ckeditor5-premium-features/ckeditor5-premium-features.css';

const data = ref( '<p>Hello world!</p>' );

const config = computed( () => {
  return {
    plugins: [ Essentials, Paragraph, Bold, Italic, FormatPainter ],
    toolbar: [ 'undo', 'redo', '|', 'bold', 'italic', '|', 'formatPainter' ]
  };
} );
</script>
