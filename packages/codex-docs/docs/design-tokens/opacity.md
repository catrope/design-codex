<script setup>
import TokensTable from '../../src/components/tokens/TokensTable.vue';
import { opacity } from '@wikimedia/codex-design-tokens/dist/index.json';
</script>

# Opacity

<TokensTable
	:tokens="opacity"
	token-demo="OpacityDemo"
/>
