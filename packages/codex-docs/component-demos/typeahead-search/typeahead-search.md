<script setup>
import TypeaheadSearchWikipedia from './../../component-demos/typeahead-search/examples/TypeaheadSearchWikipedia.vue';
import TypeaheadSearchWikidata from './../../component-demos/typeahead-search/examples/TypeaheadSearchWikidata.vue';
import TypeaheadSearchInitialValue from './../../component-demos/typeahead-search/examples/TypeaheadSearchInitialValue.vue';
</script>

::: tip TextInput props apply
This component contains a TextInput component. You can bind [TextInput props](./text-input.html#usage)
to this component and they will be passed to the TextInput within.
:::

::: tip Attributes passed to input
This component will pass any HTML attributes applied to it, except for CSS class, to the `<input>`
element within the component.
:::

## Demos

### Search Wikipedia articles

This implementation of TypeaheadSearch fetches articles from English Wikipedia.
Note that the input expands on focus via the `autoExpandWidth` prop.  Open the
console to see emitted events.

<Wrapper>
<template v-slot:demo>
<TypeaheadSearchWikipedia />
</template>
<template v-slot:code>

<<< @/../component-demos/typeahead-search/examples/TypeaheadSearchWikipedia.vue

</template>
</Wrapper>

### Search Wikidata items

In this example, results are fetched from Wikidata. Note that thumbnails are hidden via the
`hideThumbnail` prop. Open the console to see emitted events.

<Wrapper>
<template v-slot:demo>
<TypeaheadSearchWikidata />
</template>
<template v-slot:code>

<<< @/../component-demos/typeahead-search/examples/TypeaheadSearchWikidata.vue

</template>
</Wrapper>

### With initial input value

The `initialInputValue` prop can be used to pass in the initial value of the TextInput. This is
useful when replacing a server-rendered UI where the user may have started typing a search query, or
for pre-populating the search term when a user navigates back to a page where they had previously
entered one.

On mount, TypeaheadSearch will fetch search results for the initial input value if it's provided.
After that, the input value is tracked internally and will be emitted up to the parent component
when the value changes.

<Wrapper>
<template v-slot:demo>
<TypeaheadSearchInitialValue initial-input-value="Color" />
</template>
<template v-slot:code>

<<< @/../component-demos/typeahead-search/examples/TypeaheadSearchInitialValue.vue

</template>
</Wrapper>

<style scoped>
.vp-wrapper :deep( .cdx-typeahead-search ) {
	margin-bottom: 16px;
}
</style>
