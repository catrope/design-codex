<template>
	<div>
		<cdx-lookup
			v-model="selection"
			class="vp-lookup-custom-option"
			:options="menuOptions"
			@new-input="onInput"
		>
			<template #menu-option="{ option }">
				<p class="vp-lookup-custom-option__label">
					{{ option.label || option.value }}
				</p>
				<p v-if="option.description" class="vp-lookup-custom-option__description">
					{{ option.description }}
				</p>
			</template>
		</cdx-lookup>
	</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { CdxLookup, MenuOption } from '@wikimedia/codex';
import vegetableItems from './data';

export default defineComponent( {
	name: 'LookupCustomOption',
	components: { CdxLookup },
	setup() {
		const selection = ref( '' );
		const menuOptions = ref<MenuOption[]>( [] );

		function onInput( value: string ) {
			if ( value ) {
				menuOptions.value = vegetableItems.filter( ( item ) =>
					item.label.includes( value )
				);
			}
		}

		return {
			selection,
			menuOptions,
			onInput
		};
	}
} );
</script>

<style lang="less" scoped>
.vp-lookup-custom-option {
	p {
		margin: 0;
	}

	&__label {
		font-weight: bold;
	}

	&__description {
		font-size: 0.875em;
		line-height: 1.25;
	}
}
</style>
