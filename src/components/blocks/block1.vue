<template>
	<div>
	 <div class="center-block center-block_1" :class="{'block-width-100-left-230': isActive,'':positionBlock1 == 0,
		'block-width-420 block-left-40 block-width-0':positionBlock1 == 1,'block-width-420 block-left-40':positionBlock1 == 2,
		'block-left-460':positionBlock1 == 3,
		'block-left-40':positionBlock1 == 4,
		'block-left-40 block-width-580':positionBlock1 == 5,
		'block-left-460 block-left-40 block-width-580':positionBlock1 == 7}">
			<div class="header-block">
				<div class="block-btns-men hide-scroll">
					<button>Принять</button>
					<button>Добавить задачу</button>
					<button>...</button>
				</div>
				<div class="icon-hide" title="Скрыть меню" @click="closeBlockWithAnIconArrow()">
					<img :src="`${publicUrl}img/uikit/arrow.svg`">
				</div>
				<ul class="project-list">
					<li>Список проектов</li>
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
				<div class="main-block" data-block="1">
					<p class="list-item" @click="anemizeFirstTheBlock()">
						Lorem ipsum
					</p>
					<p class="list-item" @click="anemizeFirstTheBlock()">
						Lorem ipsum
					</p>
					<p class="list-item" @click="anemizeFirstTheBlock()">
						Lorem ipsum
					</p>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		props:['positionBlock1','isActive','anemizeFirstTheBlock','closeBlockWithAnIconArrow'],
		data: function() {
			return {
				hello: 'Hello'
			}
		},
		components: {}
	}
</script>

<style>

</style>