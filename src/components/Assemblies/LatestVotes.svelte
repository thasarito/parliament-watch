<script lang="ts">
	import VoteIcon from '$components/icons/VoteIcon.svelte';
	import type { Party } from '$models/party';
	import { ArrowRight } from 'carbon-icons-svelte';
	import type { VoteCardProps } from '../../routes/assemblies/[id]/+page';
	import VoteCard from '$components/VoteCard/VoteCard.svelte';
	export let votes: VoteCardProps[] = [];

	const defaultParty: Party = {
		name: '',
		color: '',
		logo: ''
	};
</script>

<div class="md:py-[32px] py-[16px]">
	<div class="flex items-center p-[16px]">
		<VoteIcon class="w-[32px] h-[32px]" />
		<span class="fluid-heading-04 ml-[16px]">ผลการลงมติล่าสุด</span>
	</div>
	<div class="border-b-[1px] border-solid border-gray-20 w-full" />
	<div class="grid md:grid-cols-3 grid-cols-1 gap-[8px] mt-[16px] justify-items-center">
		{#each votes as vote}
			<VoteCard {...vote} />
		{/each}
		<!-- TODO: fill link -->
		<a
			href="/"
			class="w-full max-w-[288px] h-full bg-blue-60 flex text-[#FFFFFF] justify-between hover:bg-blue-70"
		>
			<span class="fluid-heading-04 p-[16px]">ดูรายชื่อสมาชิกทั้งหมด</span>
			<div class="pr-[16px] pb-[16px] flex items-end">
				<ArrowRight />
			</div>
		</a>
	</div>
</div>
