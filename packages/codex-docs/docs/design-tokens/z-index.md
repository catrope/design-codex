<script setup>
import TokensTable from '../../src/components/tokens/TokensTable.vue';
import tokens from '@wikimedia/codex-design-tokens/dist/index.json';
</script>

# Z-Index

<TokensTable
	:tokens="tokens['z-index']"
/>
