<script setup>
import LookupDefault from '@/../component-demos/lookup/examples/LookupDefault.vue';
import LookupWithCustomOption from '@/../component-demos/lookup/examples/LookupWithCustomOption.vue';
import LookupNoResults from '@/../component-demos/lookup/examples/LookupNoResults.vue';
import LookupWithFetch from '@/../component-demos/lookup/examples/LookupWithFetch.vue';
import LookupClearableStartIcon from '@/../component-demos/lookup/examples/LookupClearableStartIcon.vue';
import LookupWithPlaceholder from '@/../component-demos/lookup/examples/LookupWithPlaceholder.vue';
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

### Default

The Lookup component will emit `new-input` events on input, which the parent component can
react to by computing or fetching options, then providing those options to the Lookup component for
display.

Note that in this example, options are Wikidata items with a human-readable label and a Wikidata
entity ID value.

<Wrapper>
<template v-slot:demo>
<LookupDefault />
</template>
<template v-slot:code>

<<< @/../component-demos/lookup/examples/LookupDefault.vue

</template>
</Wrapper>

### With custom option format

The `menu-option` slot can be used to set up custom option content and formatting.

<Wrapper>
<template v-slot:demo>
<LookupWithCustomOption />
</template>
<template v-slot:code>

<<< @/../component-demos/lookup/examples/LookupWithCustomOption.vue

</template>
</Wrapper>

### With footer content

The `footer` slot can be used to display non-interactive content below the final option. For
example, a "no result found" message can be conditionally displayed.

<Wrapper>
<template v-slot:demo>
<LookupNoResults />
</template>
<template v-slot:code>

<<< @/../component-demos/lookup/examples/LookupNoResults.vue

</template>
</Wrapper>

### With fetched results

Often, a Lookup component is used to fetch results from an API endpoint. Parent components can react
to the `new-input` event emitted by Lookup to search for results, then pass back to the
Lookup either an array of results to display as options or an empty array if there are no results.
Between those two events, a pending state animation will display in the input.

<Wrapper>
<template v-slot:demo>
<LookupWithFetch />
</template>
<template v-slot:code>

<<< @/../component-demos/lookup/examples/LookupWithFetch.vue

</template>
</Wrapper>

### Clearable, with start icon

Props of the TextInput component can be bound to Lookup and will be passed down to the TextInput
component inside of it, so you can take advantage of features like the "clear" button and icons.

<Wrapper>
<template v-slot:demo>
<LookupClearableStartIcon />
</template>
<template v-slot:code>

<<< @/../component-demos/lookup/examples/LookupClearableStartIcon.vue

</template>
</Wrapper>

### With placeholder

Attributes (except for `class`) will fall through to the input element, so you can set things like
`placeholder` on the Lookup component and they'll be applied to the input.

<Wrapper>
<template v-slot:demo>
<LookupWithPlaceholder />
</template>
<template v-slot:code>

<<< @/../component-demos/lookup/examples/LookupWithPlaceholder.vue

</template>
</Wrapper>
