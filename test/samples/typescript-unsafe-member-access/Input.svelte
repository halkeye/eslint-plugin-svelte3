<script lang="ts" context="module">
	const context_safe = [];
	const context_unsafe: any = null;

	console.log(context_safe.length);
	console.log(context_unsafe.length);
</script>

<script lang="ts">
	import { writable } from 'svelte/store';
	import { external_safe, external_unsafe } from './external-file';
	const instance_safe = [];
	const instance_unsafe: any = null;
	$: reactive_safe = instance_safe;
	$: reactive_unsafe = instance_unsafe;
	const writable_safe = writable([]);
	const writable_unsafe = writable(null as any);

	console.log(context_safe.length);
	console.log(context_unsafe.length);
	console.log(external_safe.length);
	console.log(external_unsafe.length);
	console.log(instance_safe.length);
	console.log(instance_unsafe.length);
	// console.log(reactive_safe.length);  TODO, current limitation
	console.log(reactive_unsafe.length);
	// console.log($writable_safe.length);  TODO, current limitation
	console.log($writable_unsafe.length);
</script>

{context_safe.length}
{context_unsafe.length}
{external_safe.length}
{external_unsafe.length}
{instance_safe.length}
{instance_unsafe.length}
<!-- {reactive_safe.length} TODO, current limitation -->
{reactive_unsafe.length}
<!-- {$writable_safe.length} TODO, current limitation -->
{$writable_unsafe.length}
