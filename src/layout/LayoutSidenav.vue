<template>
    <sidenav :orientation="orientation" :class="curClasses">

        <!-- Brand demo (see src/demo.css) -->
        <div class="app-brand demo" v-if="orientation !== 'horizontal'">
            <span class="app-brand-logo demo bg-primary">
                <svg viewBox="0 0 148 80" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                    <defs>
                        <linearGradient id="a" x1="46.49" x2="62.46" y1="53.39" y2="48.2" gradientUnits="userSpaceOnUse">
                            <stop stop-opacity=".25" offset="0"></stop>
                            <stop stop-opacity=".1" offset=".3"></stop>
                            <stop stop-opacity="0" offset=".9"></stop>
                        </linearGradient>
                        <linearGradient id="e" x1="76.9" x2="92.64" y1="26.38" y2="31.49" xlink:href="#a"></linearGradient>
                        <linearGradient id="d" x1="107.12" x2="122.74" y1="53.41" y2="48.33" xlink:href="#a"></linearGradient>
                    </defs>
                    <path style="fill: #fff;" transform="translate(-.1)" d="M121.36,0,104.42,45.08,88.71,3.28A5.09,5.09,0,0,0,83.93,0H64.27A5.09,5.09,0,0,0,59.5,3.28L43.79,45.08,26.85,0H.1L29.43,76.74A5.09,5.09,0,0,0,34.19,80H53.39a5.09,5.09,0,0,0,4.77-3.26L74.1,35l16,41.74A5.09,5.09,0,0,0,94.82,80h18.95a5.09,5.09,0,0,0,4.76-3.24L148.1,0Z"></path>
                    <path transform="translate(-.1)" d="M52.19,22.73l-8.4,22.35L56.51,78.94a5,5,0,0,0,1.64-2.19l7.34-19.2Z" fill="url(#a)"></path>
                    <path transform="translate(-.1)" d="M95.73,22l-7-18.69a5,5,0,0,0-1.64-2.21L74.1,35l8.33,21.79Z" fill="url(#e)"></path>
                    <path transform="translate(-.1)" d="M112.73,23l-8.31,22.12,12.66,33.7a5,5,0,0,0,1.45-2l7.3-18.93Z" fill="url(#d)"></path>
                </svg>
            </span>
            <router-link to="/" class="app-brand-text demo sidenav-text font-weight-normal ml-2">Appwork</router-link>
            <a href="javascript:void(0)" class="layout-sidenav-toggle sidenav-link text-large ml-auto" @click="toggleSidenav()">
                <i class="ion ion-md-menu align-middle"></i>
            </a>
        </div>
        <div class="sidenav-divider mt-0" v-if="orientation !== 'horizontal'"></div>

        <!-- Links -->
        <ul class="sidenav-inner d-flex" :class="{ 'py-1': orientation !== 'horizontal' }">

            <!-- Каталог товаров -->
            <draggable handle=".handle" group="drags" class="d-flex">
                <li>
                    <sidenav-menu :active="isMenuActive('/сatalog')" :open="isMenuOpen('/сatalog')">
                        <template slot="link-text">
                            <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                            Каталог товаров
                        </template>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-folder-open"></i>
                                Номенклатура
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Категории
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-menu :active="isMenuActive('/сatalog/articles')" :open="isMenuOpen('/сatalog/articles')" class=" sidenav-link-cell">
                            <template slot="link-text">
                                ЭКСПОРТ / ИМПОРТ .XLS
                            </template>
                            <sidenav-router-link to="#">
                                Импорт.xlc
                            </sidenav-router-link>
                            <sidenav-router-link to="#">
                                Экспорт.xlc
                            </sidenav-router-link>
                        </sidenav-menu>
                        <sidenav-router-link to="#" :exact="true" class=" sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Характеристики / значения
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                    </sidenav-menu>
                </li>
            </draggable>

            <!-- Склад -->
            <draggable class="d-flex" handle=".handle" group="drags">
                <li>
                    <sidenav-menu :active="isMenuActive('/layouts')" :open="isMenuOpen('/layouts')">
                        <template slot="link-text">
                            <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                            Склад
                        </template>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-folder-open"></i>
                                Наличие товара
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-menu :active="isMenuActive('/сatalog/articles')" :open="isMenuOpen('/сatalog/articles')" class="sidenav-link-cell">
                            <template slot="link-text">
                                НАКЛАДНЫЕ
                            </template>
                            <sidenav-router-link to="#">
                                Приход товара
                            </sidenav-router-link>
                            <sidenav-router-link to="#">
                                Расход товара
                            </sidenav-router-link>
                        </sidenav-menu>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Перемещение товара
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Инвентаризация
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Списания
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Разукомплектация
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                    </sidenav-menu>
                </li>
            </draggable>

            <!-- Закупки -->
            <draggable class="d-flex" handle=".handle" group="drags">
                <li>
                    <sidenav-menu :active="isMenuActive('/layouts')" :open="isMenuOpen('/layouts')">
                        <template slot="link-text">
                            <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                            Закупки
                        </template>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-folder-open"></i>
                                Счета
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Контракты (договора)
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                План закупок
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                    </sidenav-menu>
                </li>
            </draggable>

            <!-- Продажи -->
            <draggable class="d-flex" handle=".handle" group="drags">
                <li>
                    <sidenav-menu :active="isMenuActive('/layouts')" :open="isMenuOpen('/layouts')">
                        <template slot="link-text">
                            <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                            Продажи
                        </template>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-folder-open"></i>
                                Заявки на продажу
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Коммерческое предложение
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Счета
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Контракты (Договора)
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Акты выполненных работ
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                План продаж
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                    </sidenav-menu>
                </li>
            </draggable>

            <!-- Логистика -->
<!--            <draggable class="d-flex" handle=".handle" group="drags">-->
                    <sidenav-menu  :open="isMenuOpen('/layouts')">
                        <template slot="link-text">
                            <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                            Логистика
                        </template>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-folder-open"></i>
                                Заявки на доставку
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Доставки
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Счета
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Маршрутные листы
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Товарно-транспортные накладные
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Транспортные тарифы
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                    </sidenav-menu>
<!--            </draggable>-->

        </ul>
        <div class="block-icons">
            <i class="run-drag" @click="showElement = !showElement">
                &#9776;
            </i>
            <div class="block-menu" :class="{'show-block-menu': showElement}">
                    <!-- Задачи(CRM) -->
                    <draggable class="d-flex" handle=".handle" group="drags">
                            <sidenav-menu :active="isMenuActive('/layouts')" :open="isMenuOpen('/layouts')">
                                <template slot="link-text">
                                    <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                                    Задачи(CRM)
                                </template>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        Задачи
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        Календарь задач
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        Проекты
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        Заявки
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        События
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        Сообщения
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                                <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                                    <span class="sidenav-link-header">
                                        <i class="fas fa-info-circle"></i>
                                        Сoll-center
                                    </span>
                                    <span class="sidenav-link-description">
                                        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                                    </span>
                                </sidenav-router-link>
                            </sidenav-menu>
                    </draggable>
                    
                             <!-- Финансы -->
            <draggable class="d-flex" handle=".handle" group="drags">
                    <sidenav-menu :active="isMenuActive('/layouts')" :open="isMenuOpen('/layouts')">
                        <template slot="link-text">
                            <img :src="`${publicUrl}img/uikit/points.svg`" class="icon-points handle">
                            Финансы
                        </template>
                        <sidenav-menu :active="isMenuActive('/сatalog/articles')" :open="isMenuOpen('/сatalog/articles')" class="sidenav-link-cell">
                            <template slot="link-text">
                                ДВИЖЕНИЕ ДЕНЕГ
                            </template>
                            <sidenav-router-link to="#">
                                Приход
                            </sidenav-router-link>
                            <sidenav-router-link to="#">
                                Расход
                            </sidenav-router-link>
                        </sidenav-menu>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Счета
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Касса
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Банковская выписка
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Платежные системы
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                        <sidenav-router-link to="#" :exact="true" class="sidenav-link-cell">
                            <span class="sidenav-link-header">
                                <i class="fas fa-info-circle"></i>
                                Товарно-транспортные накладные
                            </span>
                            <span class="sidenav-link-description">
                                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                            </span>
                        </sidenav-router-link>
                    </sidenav-menu>
            </draggable>
            </div>
            <i class="show-right-block" @click="showRightPanel">?</i>
        </div>
    </sidenav>
</template>

<script>
    import {
        Sidenav,
        SidenavLink,
        SidenavRouterLink,
        SidenavMenu,
        SidenavHeader,
        SidenavBlock,
        SidenavDivider
    } from '@/vendor/libs/sidenav'
    import draggable from 'vuedraggable/src/vuedraggable'

    export default {
        name: 'app-layout-sidenav',
        components: {
            /* eslint-disable vue/no-unused-components */
            draggable,
            Sidenav,
            SidenavLink,
            SidenavRouterLink,
            SidenavMenu,
            SidenavHeader,
            SidenavBlock,
            SidenavDivider
            /* eslint-enable vue/no-unused-components */
        },
        props: {
            orientation: {
                type: String,
                default: 'vertical'
            },

        },
        data: function() {
            return {
                showElement: false,
            }
        },
        computed: {
            curClasses() {
                let bg = this.layoutSidenavBg

                if (this.orientation === 'horizontal' && (bg.indexOf(' sidenav-dark') !== -1 || bg.indexOf(' sidenav-light') !== -1)) {
                    bg = bg
                        .replace(' sidenav-dark', '')
                        .replace(' sidenav-light', '')
                        .replace('-darker', '')
                        .replace('-dark', '')
                }

                return `bg-${bg} ` + (
                    this.orientation !== 'horizontal' ?
                    'layout-sidenav' :
                    'layout-sidenav-horizontal container-p-x flex-grow-0'
                )
            }
        },

        methods: {
            isMenuActive(url) {
                return this.$route.path.indexOf(url) === 0
            },

            isMenuOpen(url) {
                return this.$route.path.indexOf(url) === 0 && this.orientation !== 'horizontal'
            },

            toggleSidenav() {
                this.layoutHelpers.toggleCollapsed()
            },

            showRightPanel() {
                this.$emit('onRightPanel', '');
            }
        }
    }
</script>