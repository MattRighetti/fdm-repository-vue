<template>
    <article class="markdown" v-html="markdownHtml"></article>
</template>

<script>
import marked from 'marked'

export default {
    name: 'markdownfield',
    props: {
        markdownText: String
    },
    computed: {
        markdownHtml: {
            get() {
                return marked(markdownText)
            }
        }
    }
}
</script>

<style>
/* Additional vertical padding used by kbd tag. */
.py-05 {
    padding-top: 0.125rem;
    padding-bottom: 0.125rem;
}

.markdown {
    @apply text-gray-900;
    @apply leading-normal;
    @apply break-words;
}

.markdown>*+* {
    @apply mt-0;
    @apply mb-4;
}

.markdown li+li {
    @apply mt-1;
}

.markdown li>p+p {
    @apply mt-6;
}

.markdown strong {
    @apply font-semibold;
}

.markdown a {
    @apply text-blue-600;
    @apply font-semibold;
}

.markdown strong a {
    @apply font-bold;
}

.markdown h1 {
    @apply leading-tight;
    @apply border-b;
    @apply text-4xl;
    @apply font-semibold;
    @apply mb-4;
    @apply mt-6;
    @apply pb-2;
}

.markdown h2 {
    @apply leading-tight;
    @apply border-b;
    @apply text-2xl;
    @apply font-semibold;
    @apply mb-4;
    @apply mt-6;
    @apply pb-2;
}

.markdown h3 {
    @apply leading-snug;
    @apply text-lg;
    @apply font-semibold;
    @apply mb-4;
    @apply mt-6;
}

.markdown h4 {
    @apply leading-none;
    @apply text-base;
    @apply font-semibold;
    @apply mb-4;
    @apply mt-6;
}

.markdown h5 {
    @apply leading-tight;
    @apply text-sm;
    @apply font-semibold;
    @apply mb-4;
    @apply mt-6;
}

.markdown h6 {
    @apply leading-tight;
    @apply text-sm;
    @apply font-semibold;
    @apply text-gray-600;
    @apply mb-4;
    @apply mt-6;
}

.markdown blockquote {
    @apply text-base;
    @apply border-l-4;
    @apply border-gray-300;
    @apply pl-4;
    @apply pr-4;
    @apply text-gray-600;
}

.markdown code {
    @apply font-mono;
    @apply text-sm;
    @apply inline;
    @apply bg-gray-200;
    @apply rounded;
    @apply px-1;
    @apply py-05;
}

.markdown pre {
    @apply bg-gray-100;
    @apply rounded;
    @apply p-4;
}

.markdown pre code {
    @apply block;
    @apply bg-transparent;
    @apply p-0;
    @apply overflow-visible;
    @apply rounded-none;
}

.markdown ul {
    @apply text-base;
    @apply pl-8;
    @apply list-disc;
}

.markdown ol {
    @apply text-base;
    @apply pl-8;
    @apply list-decimal;
}

.markdown kbd {
    @apply text-xs;
    @apply inline-block;
    @apply rounded;
    @apply border;
    @apply px-1;
    @apply py-05;
    @apply align-middle;
    @apply font-normal;
    @apply font-mono;
    @apply shadow;
}

.markdown table {
    @apply text-base;
    @apply border-gray-600;
}

.markdown th {
    @apply border;
    @apply py-1;
    @apply px-3;
}

.markdown td {
    @apply border;
    @apply py-1;
    @apply px-3;
}

/* Override pygments style background color. */
.markdown .highlight pre {
    @apply bg-gray-100 /* !important */;
}
</style>
