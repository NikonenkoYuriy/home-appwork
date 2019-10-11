<template>
	<div class="container-fluid main">
		<div class="left-menu" :class="{'left-menu__show': isActive}">
			<div class="left-gray-block gray-block"></div>
			<div class="left-icon-hide" title="Скрыть меню" @click="animateLeftBlock()" :class="{'hide-element': !isActive}">
				<svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 284.929 284.929" xml:space="preserve">
					<path d="M165.304,142.468L277.517,30.267c1.902-1.903,2.847-4.093,2.847-6.567c0-2.475-0.951-4.665-2.847-6.567L263.239,2.857C261.337,0.955,259.146,0,256.676,0c-2.478,0-4.665,0.955-6.571,2.857L117.057,135.9c-1.903,1.903-2.853,4.093-2.853,6.567c0,2.475,0.95,4.664,2.853,6.567l133.048,133.043c1.903,1.906,4.086,2.851,6.564,2.851c2.478,0,4.66-0.947,6.563-2.851l14.277-14.267c1.902-1.903,2.851-4.094,2.851-6.57c0-2.472-0.948-4.661-2.851-6.564L165.304,142.468z"></path>
					<path d="M55.668,142.468L167.87,30.267c1.903-1.903,2.851-4.093,2.851-6.567c0-2.475-0.947-4.665-2.851-6.567L153.6,2.857C151.697,0.955,149.507,0,147.036,0c-2.478,0-4.668,0.955-6.57,2.857L7.417,135.9c-1.903,1.903-2.853,4.093-2.853,6.567c0,2.475,0.95,4.664,2.853,6.567l133.048,133.043c1.902,1.906,4.09,2.851,6.57,2.851c2.471,0,4.661-0.947,6.563-2.851l14.271-14.267c1.903-1.903,2.851-4.094,2.851-6.57c0-2.472-0.947-4.661-2.851-6.564L55.668,142.468z"></path>
				</svg>
			</div>
			<div class="left-panel-hide" @click="animateLeftBlock()" :class="{'show-block': !isActive}">
				<div class="left-block-points" data-hide-center-block="true">
					<span></span>
					<span></span>
					<span></span>
				</div>
			</div>
		</div>
		<app-block1 
		:positionBlock1="positionBlock1" 
		:isActive="isActive" :anemizeFirstTheBlock="anemizeFirstTheBlock" :closeBlockWithAnIconArrow="closeBlockWithAnIconArrow">
		</app-block1>
		<app-block2 
		 :positionBlock2="positionBlock2" :hideTwoTheBlock="hideTwoTheBlock" :anemizeTwoTheBlock="anemizeTwoTheBlock" :closeBlockWithAnIconArrow="closeBlockWithAnIconArrow">
		 </app-block2>
		<app-block3  
		 :positionBlock3="positionBlock3" :hideTreeTheBlock="hideTreeTheBlock" :closeBlockWithAnIconArrow="closeBlockWithAnIconArrow">
		 </app-block3>
		<div class="right-panel-zpane" :class="{'zpane-right-0': rightPanel}">
			<div class="right-gray-block gray-block"></div>
			<div class="right-panel-item" @click="showBlockRight(1)">
				&#9742;
				<div class="popover-content">
					<div class="popover-text">
						This is your content
					</div>
				</div>
			</div>
			<div class="right-panel-item" @click="showBlockRight(2)">
				&#10001;
				<div class="popover-content">
					<div class="popover-text">
						This is your
					</div>
				</div>
			</div>
			<div class="right-panel-item" @click="showBlockRight(3)">
				&#9734;
				<div class="popover-content">
					<div class="popover-text">
						This
					</div>
				</div>
			</div>
			<div class="right-panel-item" @click="showBlockRight(4)">
				&#9885;
				<div class="popover-content">
					<div class="popover-text">
						This is your
					</div>
				</div>
			</div>
			<div class="right-panel-item" @click="showBlockRight(5)">
				&#10002;
				<div class="popover-content">
					<div class="popover-text">
						This is your
					</div>
				</div>
			</div>
			<div class="right-panel-item" @click="showBlockRight(6)">
				&#9745;
				<div class="popover-content">
					<div class="popover-text">
						This is your
					</div>
				</div>
			</div>
		</div>
		<div class="tabs-block" :class="{'tabs-block-show': rightBlock,
						'tabs-block-show block-right-40':rightBlockWidth100}">
			<div class="block-resizes" data-block-resizes="right"></div>
			<div class="tab-block" :class="{'show-block':rightBlockContent == 1}">
				<div class="tab-block-header">
					<div class="block-close" @click="hideBlockRight()">
						<span></span>
						<span></span>
					</div>
				</div>
				<div class="tab-block-text">
					<p v-for="item in items">text 1</p>
				</div>
			</div>
			<div class="tab-block" :class="{'show-block':rightBlockContent == 2}">
				<div class="tab-block-header">
					<div class="block-close" @click="hideBlockRight()">
						<span></span>
						<span></span>
					</div>
				</div>
				<div class="tab-block-text">
					<p v-for="item in items">text 2</p>
				</div>
			</div>
			<div class="tab-block" :class="{'show-block':rightBlockContent == 3}">
				<div class="tab-block-header">
					<div class="block-close" @click="hideBlockRight()">
						<span></span>
						<span></span>
					</div>
				</div>
				<div class="tab-block-text">
					<p v-for="item in items">text 3</p>
				</div>
			</div>
			<div class="tab-block" :class="{'show-block':rightBlockContent == 4}">
				<div class="tab-block-header">
					<div class="block-close" @click="hideBlockRight()">
						<span></span>
						<span></span>
					</div>
				</div>
				<div class="tab-block-text">
					<p v-for="item in items">text 4</p>
				</div>
			</div>
			<div class="tab-block" :class="{'show-block':rightBlockContent == 5}">
				<div class="tab-block-header">
					<div class="block-close" @click="hideBlockRight()">
						<span></span>
						<span></span>
					</div>
				</div>
				<div class="tab-block-text">
					<p>text 5</p>
				</div>
			</div>
			<div class="tab-block" :class="{'show-block':rightBlockContent == 6}">
				<div class="tab-block-header">
					<div class="block-close" @click="hideBlockRight()">
						<span></span>
						<span></span>
					</div>
				</div>
				<div class="tab-block-text">
					<p v-for="item in items">text 6</p>
				</div>
			</div>
		</div>


		<div class="content-block-right"
		:class="{'show-content-block-right':showRightPanel}">
			<div class="content-block-head"
			@click="hideRightPanel">
				<div class="block-right-close">
					<span></span>
					<span></span>
				</div>
			</div>
			<div class="wrapper-content">
				<div class="content-block-menu">
					<div class="right-content-item  activ-item">
						&#9742;
						<div class="popover-content-wrapper">
							<div class="popover-text">
								This is your content
							</div>
						</div>
					</div>
					<div class="right-content-item">
						&#10001;
						<div class="popover-content-wrapper">
							<div class="popover-text">
								This
							</div>
						</div>
					</div>
					<div class="right-content-item">
						&#9734;
						<div class="popover-content-wrapper">
							<div class="popover-text">
								This is your
							</div>
						</div>
					</div>
					<div class="right-content-item">
						&#9885;
						<div class="popover-content-wrapper">
							<div class="popover-text">
								This is your
							</div>
						</div>
					</div>
					<div class="right-content-item">
						&#10002;
						<div class="popover-content-wrapper">
							<div class="popover-text">
								This is your
							</div>
						</div>
					</div>
					<div class="right-content-item">
						&#9745;
						<div class="popover-content-wrapper">
							<div class="popover-text">
								This is your
							</div>
						</div>
					</div>
				</div>
				<div class="main-content">
					<div class="content-box">
						<p class="box-text">Text 1</p>
					</div>
					<div class="content-box">
						<p class="box-text">Text 2</p>
					</div>
					<div class="content-box">
						<p class="box-text">Text 3</p>
					</div>
					<div class="content-box">
						<p class="box-text">Text 4</p>
					</div>
					<div class="content-box">
						<p class="box-text">Text 5</p>
					</div>
					<div class="content-box">
						<p class="box-text">Text 6</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	import Block1 from '../blocks/block1';
	import Block2 from '../blocks/block2';
	import Block3 from '../blocks/block3';
	//console.log(Block1);
	export default {
		props:{
            showRightPanel: Boolean
        },
		data: () => ({
			rightPanel: false,
			isActive: true,
			positionBlock1: 0,
			positionBlock2: 0,
			positionBlock3: 0,
			additionalBlockOnSide: 'left',
			rightBlock: false,
			rightBlockContent: 0,
			rightBlockWidth100: false,
			showBlock: false,
			items:[1,2,3,4,5,6,7,8,9,10]
		}),
		name: 'horizontal-sidenav-example',
		metaInfo: {
			title: 'Home'
		},
		components: {
			appBlock1: Block1,
			appBlock2: Block2,
			appBlock3: Block3
		},
		methods: {
			anemizeFirstTheBlock: function() {
				//console.log(1);
				if (this.positionBlock1 == 0) {
					//console.log(1.1);
					this.anemizeTheBlocks(4, 0, 0);
				} else if (this.positionBlock1 == 4) {
					//console.log(1.2);
					this.anemizeTheBlocks(2, 3, 0);

				} else if (this.positionBlock1 == 2) {
					this.anemizeTheBlocks(4, 0, 0);
				}
				this.isActive = false;
				this.rightPanel = true;
			},
			anemizeTwoTheBlock: function() {
				//console.log(2);
				if (this.positionBlock2 == 3) {
					//console.log(2.1);
					this.anemizeTheBlocks(1, 2, 3);
				} else if (this.positionBlock2 == 2) {
					//console.log(2.2);
					this.anemizeTheBlocks(1, 4, 0);
				} else if (this.positionBlock2 == 4) {
					//console.log(2.3);
					this.anemizeTheBlocks(1, 2, 3);
				}
			},
			hideTwoTheBlock: function() {
				if (this.positionBlock2 == 3) {
					this.anemizeTheBlocks(4, 0, 0);
					//console.log('two 2');
				} else if (this.positionBlock2 == 4) {
					this.anemizeTheBlocks(4, 0, 0);
					//console.log('one 1');
				}
			},
			hideTreeTheBlock: function() {
				//console.log(444);
				if (this.positionBlock2 == 1) {
					this.anemizeTheBlocks(1, 4, 0);
					//console.log('one');
				}
				if (this.positionBlock2 == 2) {
					this.anemizeTheBlocks(1, 4, 0);
					//console.log('two');
				}
			},
			anemizeTheBlocks: function(valB1, valB2, valB3) {
				this.positionBlock1 = valB1;
				this.positionBlock2 = valB2;
				this.positionBlock3 = valB3;
			},
			animateLeftBlock: function() {
				//console.log(5);
				if (this.positionBlock1 == 0 || this.positionBlock1 == 4) {
					//console.log(5.1);
					this.isActive = !this.isActive;
					this.rightPanel = false;
					this.anemizeTheBlocks(0, 0, 0);
				} else if (this.positionBlock1 == 2 && this.positionBlock2 == 3) {
					//console.log(5.2);
					this.anemizeTheBlocks(0, 0, 0);
				} else if (this.positionBlock1 == 5) {
					//console.log(5.2222);
					this.rightBlock = false;
					this.anemizeTheBlocks(4, 0, 0);
				} else if (this.positionBlock2 == 2 && this.positionBlock3 == 3) {
					//console.log(5.4);
					this.anemizeTheBlocks(2, 3, 0);
				} else if (this.positionBlock2 == 4) {
					//console.log(5.5);
					this.anemizeTheBlocks(2, 3, 0);
				} else if (this.positionBlock2 == 5) {
					//console.log(5.333);
					this.rightBlock = false;
					this.anemizeTheBlocks(1, 4, 0);
				} else if (this.positionBlock2 == 1 && this.positionBlock3 == 0 && this.rightBlockWidth100) {
					//console.log(5.333);
					this.rightBlockWidth100 = false;
					this.rightBlock = false;
					this.anemizeTheBlocks(1, 4, 0);
				} else if (this.positionBlock3 == 5) {
					//console.log(5.333);
					this.rightBlock = false;
					this.anemizeTheBlocks(1, 1, 4);
				} else if (this.positionBlock2 == 1 && this.positionBlock3 == 1 && this.rightBlockWidth100) {
					//console.log(5.4444);
					this.rightBlockWidth100 = false;
					this.rightBlock = false;
					this.anemizeTheBlocks(1, 1, 4);
				} else if (this.positionBlock3 == 4) {
					//console.log(5.6);
					this.anemizeTheBlocks(1, 2, 3);
				} else if (this.positionBlock1 == 2 && this.positionBlock2 == 6) {
					//console.log(5.7);
					this.anemizeTheBlocks(2, 3, 0);
					this.rightBlock = false;
				} else if (this.positionBlock2 == 2 && this.positionBlock3 == 6) {
					//console.log(5.8);
					this.anemizeTheBlocks(1, 2, 3);
					this.rightBlock = false;
				} else if (this.positionBlock1 == 7) {
					//console.log(5.9);
					this.anemizeTheBlocks(4, 0, 0);
					this.rightBlock = false;
				} else if (this.positionBlock2 == 7) {
					//console.log(5.9);
					this.anemizeTheBlocks(1, 4, 0);
					this.rightBlock = false;
				} else if (this.positionBlock3 == 7) {
					//console.log('5.9.1');
					this.anemizeTheBlocks(1, 1, 4);
					this.rightBlock = false;
				} else if (this.positionBlock1 == 1 && this.positionBlock2 == 0 && this.rightBlockWidth100) {
					//console.log('5.9.2');
					this.anemizeTheBlocks(4, 0, 0);
					this.rightBlockWidth100 = false;
					this.rightBlock = false;
				}
			},
			showBlockRight: function(index) {
				this.rightBlockContent = index;
				this.rightBlock = true;
				if (this.positionBlock1 == 4) {
					this.positionBlock1 = 5;
				} else if (this.positionBlock2 == 4) {
					this.positionBlock2 = 5;
				} else if (this.positionBlock3 == 4) {
					this.positionBlock3 = 5;
				} else if (this.positionBlock2 == 3 && this.rightBlock == true) {
					this.positionBlock2 = 6;
				} else if (this.positionBlock3 == 3 && this.rightBlock == true) {
					this.positionBlock3 = 6;
				}
			},
			hideBlockRight: function() {
				//console.log(22222);
				this.rightBlock = false;
				if (this.positionBlock1 == 5) {
					this.positionBlock1 = 4;
				}
				if (this.positionBlock2 == 5) {
					this.positionBlock2 = 4;
				}
				if (this.positionBlock3 == 5) {
					this.positionBlock3 = 4;
				}
				if (this.positionBlock2 == 6) {
					this.positionBlock2 = 3;
				}
				if (this.positionBlock3 == 6) {
					this.positionBlock3 = 3;
				}
				if (this.positionBlock1 == 1 && this.positionBlock2 == 0 && this.positionBlock3 == 0) {
					this.positionBlock1 = 4;
					this.rightBlockWidth100 = false;
				}
				if (this.positionBlock1 == 1 && this.positionBlock2 == 1 && this.positionBlock3 == 0) {
					this.positionBlock2 = 4;
					this.rightBlockWidth100 = false;
				}
				if (this.positionBlock1 == 1 && this.positionBlock2 == 1 && this.positionBlock3 == 1) {
					this.positionBlock3 = 4;
					this.rightBlockWidth100 = false;
				}
				if (this.positionBlock2 == 7) {
					this.positionBlock2 = 4;
				}
				if (this.positionBlock3 == 7) {
					this.positionBlock3 = 4;
				}
			},
			closeBlockWithAnIconArrow: function() {
				//console.log(7);
				if (this.positionBlock1 == 2 && !this.rightBlock) {
					//console.log(7.1);
					this.anemizeTheBlocks(1, 4, 0);
				} else if (this.positionBlock1 == 2 && this.rightBlock) {
					//console.log(7.1444);
					this.anemizeTheBlocks(1, 7, 0);
				} else if (this.positionBlock2 == 2 && !this.rightBlock) {
					//console.log(7.2);
					this.anemizeTheBlocks(1, 1, 4);
				} else if (this.positionBlock2 == 2 && this.rightBlock) {
					//console.log(7.1444);
					this.anemizeTheBlocks(1, 1, 7);
				} else if (this.positionBlock1 == 5) {
					//console.log(7.3);
					this.anemizeTheBlocks(1, 0, 0);
					this.rightBlockWidth100 = true;
				} else if (this.positionBlock2 == 5) {
					//console.log(7.4);
					this.anemizeTheBlocks(1, 1, 0);
					this.rightBlockWidth100 = true;
				} else if (this.positionBlock3 == 5) {
					//console.log(7.5);
					this.anemizeTheBlocks(1, 1, 1);
					this.rightBlockWidth100 = true;
				} else if (this.positionBlock2 == 7 && this.rightBlock) {
					//console.log(7.6);
					this.anemizeTheBlocks(1, 1, 0);
					this.rightBlockWidth100 = true;
				} else if (this.positionBlock3 == 7 && this.rightBlock) {
					//console.log(7.6);
					this.anemizeTheBlocks(1, 1, 1);
					this.rightBlockWidth100 = true;
				}
			},
            hideRightPanel: function () {
               this.$emit('onRightPanelHide', '');
            }
		}
	}

</script>
