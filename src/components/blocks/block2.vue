<template>
	<div>
			<div class="center-block center-block_2" :class="{'':positionBlock2 == 0,
						'block-width-420 block-left-40 block-width-0':positionBlock2 == 1,'block-width-420 block-left-40':positionBlock2 == 2,
						'block-left-460':positionBlock2 == 3,
						'block-left-40':positionBlock2 == 4,
						'block-left-40 block-width-580':positionBlock2 == 5,
						'block-left-460 block-left-460-width-1000':positionBlock2 == 6,
						'block-left-460 block-left-40 block-width-580':positionBlock2 == 7}">
			<div class="block-resizes" data-block-resizes="main"></div>

			<div class="header-block" @click="hideTwoTheBlock()">
				<div class="block-btns-men hide-scroll">
					<button>Принять</button>
					<button>Добавить задачу</button>
					<button>...</button>
				</div>
				<div class="icon-hide" title="Скрыть меню" @click="closeBlockWithAnIconArrow()">
					<img :src="`${publicUrl}img/uikit/arrow.svg`">
				</div>
				<div class="b-last-block-close" data-block-close="2">
					<span></span>
					<span></span>
				</div>
				<ul class="project-list">
					<li>Список задач</li>
				</ul>
				<div class="task-current-status hide-scroll">
					<span class="task-current-status-label">
						Текущий статус:
					</span>
					<span class="task-current-status-text">
						<div class="status-color-dot">
							<span></span>
						</div>
						<span class="status-text">
							Новая
						</span>
					</span>
				</div>
			</div>

			<div class="wrapper-block">
				<div class="main-block" data-block="2">
					<p class="list-item" @click="anemizeTwoTheBlock()">
						Lorem ipsum
					</p>
				</div>
			</div>
		</div>
	</div>   
</template>

<script>
    export default {
		props:['positionBlock2','anemizeTwoTheBlock','closeBlockWithAnIconArrow','hideTwoTheBlock'],
        data () {
            return {
            }
        },
        components: {
        }
    }
</script>

<style>
    
</style>