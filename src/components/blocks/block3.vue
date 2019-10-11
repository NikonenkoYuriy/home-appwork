<template>
	<div>
			<div class="center-block center-block_3" :class="{'':positionBlock3 == 0,
						'block-width-420 block-left-40 block-width-0':positionBlock3 == 1,'block-width-420 block-left-40':positionBlock3 == 2,
						'block-left-460':positionBlock3 == 3,
						'block-left-40':positionBlock3 == 4,
						'block-left-40 block-width-580':positionBlock3 == 5,
						'block-left-460 block-left-460-width-1000':positionBlock3 == 6,
						'block-left-460 block-left-40 block-width-580':positionBlock3 == 7}">
			<div class="block-resizes" data-block-resizes="main"></div>
			<div class="header-block">
				<div class="block-btns-men hide-scroll">
					<button>Принять</button>
					<button>Добавить задачу</button>
					<button>...</button>
				</div>
				<div class="icon-hide" title="Скрыть меню" @click="closeBlockWithAnIconArrow()">
					<img :src="`${publicUrl}img/uikit/arrow.svg`">
				</div>
				<div class="b-last-block-close" data-block-close="3" @click="hideTreeTheBlock()">
					<span></span>
					<span></span>
				</div>
				<ul class="project-list">
					<li>Задача</li>
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
				<div class="main-block">
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
					<p>Lorem ipsum</p>
				</div>
			</div>
		</div>
	</div>   
</template>

<script>
    export default {
		props:['positionBlock3','closeBlockWithAnIconArrow','hideTreeTheBlock'],
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