<template>
  <div>
    <div
      v-bind:class="currentColor"
      class="fixed inset-0 p-4 bg-gradient-to-br"
    ></div>

    <div
      class="fixed left-0 z-10 items-center justify-center hidden w-full  top-8 sm:flex"
    >
      <div
        v-bind:class="currentColor2"
        class="w-40 h-3 rounded-full opacity-100"
      ></div>
    </div>

    <div
      id="page_wrapper"
      class="fixed p-4 overflow-y-scroll bg-gray-100  lg:left-4 lg:right-4 lg:top-4 lg:bottom-4 sm:left-2 sm:top-2 sm:right-2 sm:bottom-2 left-1 top-1 right-1 bottom-1 dark:bg-gray-900 rounded-xl"
    >
      <div class="flex flex-col items-center justify-center">
        <div
          class="flex flex-col items-center justify-center w-full max-w-6xl mt-0 space-x-4  lg:mt-32 sm:mt-16 sm:flex-row space-4 sm:items-between sm:justify-between"
        >
          <div class="flex mb-4 space-x-4 sm:mb-0">
            <button
              @click="onToggleDar()"
              v-if="isDark"
              class="p-2 text-gray-600 bg-gray-200 rounded-full  dark:bg-gray-800 hover:text-gray-900 dark:text-gray-100 dark:hover:text-gray-400"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-5 h-5"
                viewBox="0 0 20 20"
                fill="currentColor"
              >
                <path
                  d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"
                />
              </svg>
            </button>

            <button
              class="p-2 text-gray-600 bg-gray-200 rounded-full  dark:bg-gray-800 hover:text-gray-900 dark:text-gray-100 dark:hover:text-gray-400"
              @click="onToggleDar()"
              v-if="!isDark"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-5 h-5"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
                />
              </svg>
            </button>
          </div>

          <div class="flex space-x-4">
            <svg
              @click="goTo(gitHubUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-green-400 dark:hover:text-green-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>GitHub</title>
              <path
                d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"
              />
            </svg>

            <svg
              @click="goTo(discordUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-green-400 dark:hover:text-green-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Discord icon</title>
              <path
                d="M20.222 0c1.406 0 2.54 1.137 2.607 2.475V24l-2.677-2.273-1.47-1.338-1.604-1.398.67 2.205H3.71c-1.402 0-2.54-1.065-2.54-2.476V2.48C1.17 1.142 2.31.003 3.715.003h16.5L20.222 0zm-6.118 5.683h-.03l-.202.2c2.073.6 3.076 1.537 3.076 1.537-1.336-.668-2.54-1.002-3.744-1.137-.87-.135-1.74-.064-2.475 0h-.2c-.47 0-1.47.2-2.81.735-.467.203-.735.336-.735.336s1.002-1.002 3.21-1.537l-.135-.135s-1.672-.064-3.477 1.27c0 0-1.805 3.144-1.805 7.02 0 0 1 1.74 3.743 1.806 0 0 .4-.533.805-1.002-1.54-.468-2.14-1.404-2.14-1.404s.134.066.335.2h.06c.03 0 .044.015.06.03v.006c.016.016.03.03.06.03.33.136.66.27.93.4.466.202 1.065.403 1.8.536.93.135 1.996.2 3.21 0 .6-.135 1.2-.267 1.8-.535.39-.2.87-.4 1.397-.737 0 0-.6.936-2.205 1.404.33.466.795 1 .795 1 2.744-.06 3.81-1.8 3.87-1.726 0-3.87-1.815-7.02-1.815-7.02-1.635-1.214-3.165-1.26-3.435-1.26l.056-.02zm.168 4.413c.703 0 1.27.6 1.27 1.335 0 .74-.57 1.34-1.27 1.34-.7 0-1.27-.6-1.27-1.334.002-.74.573-1.338 1.27-1.338zm-4.543 0c.7 0 1.266.6 1.266 1.335 0 .74-.57 1.34-1.27 1.34-.7 0-1.27-.6-1.27-1.334 0-.74.57-1.338 1.27-1.338z"
              />
            </svg>

            <svg
              @click="goTo(igUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-green-400 dark:hover:text-green-400"
              fill="currentColor"
              role="img"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Instagram icon</title>
              <path
                d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.899 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.899-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z"
              />
            </svg>

            <svg
              @click="goTo(fbUrl)"
              class="w-5 h-5 text-gray-400 transition duration-300 cursor-pointer  dark:text-gray-600 hover:text-green-400 dark:hover:text-green-400"
              fill="currentColor"
              role="img"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
            >
              <title>Facebook icon</title>
              <path
                d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
              />
            </svg>
          </div>
        </div>
        <div class="flex w-full max-w-6xl mt-4" id="intro">
          <div
            class="flex w-full p-8 space-x-0 bg-white rounded-lg  dark:bg-gray-800 sm:p-4 sm:space-x-8"
          >
            <div class="static hidden sm:block">
              <div class="relative w-40 rounded-lg cursor-pointer group h-50">
                <img src="/photo2.png" class="w-full rounded-lg" alt="" />
                <div class="absolute top-0 left-0">
                  <img
                    src="/photo.png"
                    class="w-full transition duration-300 rounded-lg opacity-0  group-hover:opacity-100"
                    alt=""
                  />
                </div>
              </div>
            </div>

            <div
              class="flex flex-col items-center justify-between w-full  lg:flex-row"
            >
              <div
                class="flex flex-col items-center justify-center w-full h-full space-y-6  lg:w-max sm:items-start sm:space-y-3"
              >
                <h1
                  class="mt-0 text-5xl font-bold text-center text-black  dark:text-gray-50 sm:mt-0 sm:text-left"
                >
                  <span class="inline text-green-400">Richard </span>
                  <span class="inline text-green-400">Nálepka </span>
                  <span class="hidden sm:inline">👋</span>
                </h1>
                <h2
                  class="mt-6 mb-4 text-2xl font-semibold text-center text-gray-400  sm:mb-0 sm:mt-0 sm:text-left"
                >
                  <span class="font-bold text-gray-900 dark:text-white"
                    >Still a learning</span
                  >
                  website developer.
                </h2>

                <!-- <p class="font-bold text-yellow-300 cursor-pointer">
              Make a payment
            </p> -->
              </div>

              <div
                class="flex flex-col items-center justify-center w-full h-full py-3 mt-6 space-y-2  lg:w-max sm:items-start lg:items-end lg:px-2 sm:mt-2"
              >
                <div
                  class="flex justify-start cursor-pointer group lg:justify-end"
                >
                  <div
                    @click="onDownloadCV()"
                    style="width: fit-content"
                    class="flex p-2 text-xl font-bold text-gray-500 transition duration-300 rounded-lg  lg:float-right dark:bg-gray-900 bg-gray-50 group-hover:bg-green-400 group-hover:text-white"
                  >
                    Download CV

                    <svg
                      class="w-6 h-6 ml-3 text-gray-500 transition duration-300  group-hover:text-white"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M6 2a2 2 0 00-2 2v12a2 2 0 002 2h8a2 2 0 002-2V7.414A2 2 0 0015.414 6L12 2.586A2 2 0 0010.586 2H6zm5 6a1 1 0 10-2 0v3.586l-1.293-1.293a1 1 0 10-1.414 1.414l3 3a1 1 0 001.414 0l3-3a1 1 0 00-1.414-1.414L11 11.586V8z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </div>
                </div>

                <div
                  class="justify-start cursor-pointer  group cursor-pointerflex lg:justify-end"
                >
                  <div
                    @click="onPrintCV()"
                    style="width: fit-content"
                    class="flex p-2 text-xl font-bold text-gray-500 transition duration-300 rounded-lg  lg:float-right dark:bg-gray-900 bg-gray-50 group-hover:bg-green-100 group-hover:text-green-400"
                  >
                    Print CV

                    <svg
                      class="w-6 h-6 ml-3 text-gray-500 transition duration-300  group-hover:text-green-400"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M5 4v3H4a2 2 0 00-2 2v3a2 2 0 002 2h1v2a2 2 0 002 2h6a2 2 0 002-2v-2h1a2 2 0 002-2V9a2 2 0 00-2-2h-1V4a2 2 0 00-2-2H7a2 2 0 00-2 2zm8 0H7v3h6V4zm0 8H7v4h6v-4z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="flex items-center justify-center">
        <div class="grid w-full max-w-6xl mt-4 gap-y-4">
          <core-portfolio-row
            :isOpened="currentlyOpened === 'skills'"
            v-on:activate="onOpenSection($event)"
            id="skills"
            colorParent="from-sky-300 to-sky-500"
            colorParent2="bg-sky-300"
            colorNameBg="bg-sky-200"
            colorNameText="text-sky-600"
            colorNameDark="text-sky-500 dark:text-sky-400"
            title="Skills Portfolio"
            iconD="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"
          >
            <div class="grid w-full grid-cols-12 gap-x-0 lg:gap-x-6 gap-y-6">
              <div class="col-span-12 xl:col-span-8">
                <div class="max-w-xs">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    I prepare
                    <span class="text-sky-500">modern websites</span> from the
                    first line of the code. Every website I build is using
                    <a
                      href="https://tailwindcss.com/"
                      target="_blank"
                      class="text-sky-500"
                    >
                      Tailwind</a
                    > and <a
                      href="https://kit.svelte.dev/"
                      target="_blank"
                      class="text-sky-500"
                    >
                      SvelteKIT.</a
                    >
                    
                  </h1>
                </div>

                <div class="grid grid-cols-12 gap-6 mt-8">
                  <div
                    class="flex flex-col col-span-12 space-y-8 md:col-span-6"
                  >
                    <div
                      class="p-6 bg-gray-100 rounded-lg dark:bg-gray-900"
                      v-for="(stackItem, stackableInex) of stackItemsLeft"
                      :key="stackableInex"
                    >
                      <div
                        v-bind:class="
                          stackItem.isSpecial ? 'bg-sky-500' : 'bg-blue-400'
                        "
                        class="flex items-center justify-center w-full h-20 rounded-lg "
                        v-html="stackItem.iconSvg"
                      ></div>

                      <div class="flex flex-col w-full mt-6 space-y-4">
                        <span
                          class="text-2xl font-bold text-black  dark:text-gray-100"
                          >{{ stackItem.title }}</span
                        >

                        <span
                          class="text-lg font-semibold text-gray-600  dark:text-gray-400"
                          >{{ stackItem.text }}</span
                        >
                      </div>
                    </div>
                  </div>
                  <div
                    class="flex flex-col col-span-12 space-y-8  md:col-span-6 md:-mt-32"
                  >
                    <div
                      class="p-6 bg-gray-100 rounded-lg dark:bg-gray-900"
                      v-for="(stackItem, index) of stackItemsRight"
                      :key="index"
                    >
                      <div
                        class="flex items-center justify-center w-full h-20 bg-blue-400 rounded-lg "
                        v-html="stackItem.iconSvg"
                      ></div>

                      <div class="flex flex-col w-full mt-6 space-y-4">
                        <span
                          class="text-2xl font-bold text-black  dark:text-gray-100"
                          >{{ stackItem.title }}</span
                        >

                        <span
                          class="text-lg font-semibold text-gray-600  dark:text-gray-400"
                          >{{ stackItem.text }}</span
                        >
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div
                class="grid w-full grid-cols-12 col-span-12  xl:col-span-4 gap-y-8"
                style="height: fit-content"
              >
                <div class="col-span-12 md:col-span-6 xl:col-span-12">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    Coding skills:
                  </h1>

                  <div class="flex flex-col mt-4 space-y-4">
                    <div
                      class="flex space-x-3"
                      v-for="(codingSkill, index) of codingSkills"
                      :key="index"
                    >
                      <div class="flex items-center justify-center">
                        <svg
                          v-bind:class="
                            codingSkill.level < i
                              ? ['text-gray-200', 'dark:text-gray-600']
                              : ['text-green-400']
                          "
                          v-for="i of [1, 2, 3, 4, 5]"
                          :key="i"
                          class="w-6 h-6"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                        >
                          <path
                            d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                          />
                        </svg>
                      </div>
                      <span
                        class="text-xl font-bold text-gray-600  dark:text-gray-300"
                      >
                        {{ codingSkill.name }}
                      </span>
                    </div>
                  </div>
                </div>

                <div class="col-span-12 md:col-span-6 xl:col-span-12">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    Technologies:
                  </h1>

                  <div class="flex flex-col mt-4 space-y-4">
                    <div
                      class="flex space-x-3"
                      v-for="(technologiesSkill, index) of technologiesSkills"
                      :key="index"
                    >
                      <div class="flex items-center justify-center">
                        <svg
                          v-bind:class="
                            technologiesSkill.level < i
                              ? ['text-gray-200', 'dark:text-gray-600']
                              : ['text-sky-500']
                          "
                          v-for="i of [1, 2, 3, 4, 5]"
                          :key="i"
                          class="w-6 h-6"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
                            clip-rule="evenodd"
                          />
                        </svg>
                      </div>
                      <span
                        class="text-xl font-bold text-gray-600  dark:text-gray-300"
                      >
                        {{ technologiesSkill.name }}
                      </span>
                    </div>
                  </div>
                </div>

                <div class="col-span-12 md:col-span-6 xl:col-span-12">
                  <h1 class="text-xl font-bold text-black dark:text-gray-50">
                    Language skills:
                  </h1>

                  <div class="flex flex-col mt-4 space-y-4">
                    <div
                      class="flex space-x-3"
                      v-for="(langSkill, index) of langSkills"
                      :key="index"
                    >
                      <div class="flex items-center justify-center">
                        <svg
                          v-bind:class="
                            langSkill.level < i
                              ? ['text-gray-200', 'dark:text-gray-600']
                              : ['text-yellow-400']
                          "
                          v-for="i of [1, 2, 3, 4, 5]"
                          :key="i"
                          class="w-6 h-6"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M11.3 1.046A1 1 0 0112 2v5h4a1 1 0 01.82 1.573l-7 10A1 1 0 018 18v-5H4a1 1 0 01-.82-1.573l7-10a1 1 0 011.12-.38z"
                            clip-rule="evenodd"
                          />
                        </svg>
                      </div>
                      <span
                        class="text-xl font-bold text-gray-600  dark:text-gray-300"
                      >
                        {{ langSkill.name }}
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </core-portfolio-row>

          <core-portfolio-row
            :isOpened="currentlyOpened === 'projects'"
            v-on:activate="onOpenSection($event)"
            id="projects"
            colorParent="from-red-300 to-red-500"
            colorParent2="bg-red-300"
            colorNameBg="bg-red-200"
            colorNameText="text-red-600"
            colorNameDark="text-red-500 dark:text-red-400"
            title="Successful Projects"
            iconD="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"
          >
            <h1 class="text-xl font-bold text-black dark:text-gray-50">
              
              <span class="text-red-400">5 finished projects</span> 
            </h1>

            <div class="grid grid-cols-12 gap-6 mt-8">
              <div
                v-for="(project, i) of projects"
                :key="i"
                v-bind:class="project.grid"
                class="relative p-2 bg-red-400 rounded-lg cursor-pointer  group h-80"
                @click="onOpenGallery(i)"
              >
                <div
                  class="w-full h-full rounded-lg"
                  v-bind:style="{
                    backgroundImage: 'url(\'' + project.mainImage + '\')',
                  }"
                  style="background-size: cover; background-position: center"
                ></div>

                <div
                  style="background-color: rgba(0, 0, 0, 0.7)"
                  class="absolute inset-0 flex flex-col items-center justify-center p-6 transition duration-300 rounded-lg opacity-0  group-hover:opacity-100"
                >
                  <h3 class="text-2xl font-bold text-center text-white">
                    {{ project.name }}
                  </h3>
                  <p
                    class="mt-3 font-semibold text-center text-gray-100 text-md"
                  >
                    {{ project.description }}
                  </p>
                </div>
              </div>
            </div>
          </core-portfolio-row>

          <core-portfolio-row
            :isOpened="currentlyOpened === 'reviews'"
            v-on:activate="onOpenSection($event)"
            id="reviews"
            colorParent="from-purple-300 to-purple-500"
            colorParent2="bg-purple-300"
            colorNameBg="bg-purple-200"
            colorNameText="text-purple-600"
            colorNameDark="text-purple-500 dark:text-purple-400"
            title="Client Reviews"
            iconD="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"
          >
            <h1 class="text-xl font-bold text-black dark:text-gray-50">
              Here's what some <span class="text-purple-400">companies</span> I
              worked with as freelancer have to say about my work.
            </h1>

            <div class="flex flex-col mt-8 space-y-16 sm:space-y-8">
              <div
                class="flex flex-col items-center justify-center space-x-0  sm:space-x-8 sm:flex-row sm:items-start sm:justify-start"
                v-for="(review, index) of reviews"
                :key="index"
              >
                <img :src="review.image" class="w-40 rounded-lg" alt="" />
                <div>
                  <h1
                    class="mt-6 text-3xl font-bold text-center text-black  dark:text-gray-50 sm:mt-0 sm:text-left"
                  >
                    {{ review.name }}
                  </h1>
                  <h3
                    class="text-xl font-bold text-center text-purple-400  sm:text-left"
                  >
                    {{ review.company }}
                  </h3>

                  <div
                    class="hidden w-40 h-1 mt-2 bg-gray-200 rounded-full  sm:block dark:bg-gray-700"
                  ></div>

                  <p
                    class="mt-2 text-lg font-semibold text-center sm:text-left"
                  >
                    {{ review.text }}
                  </p>
                </div>
              </div>
            </div>
          </core-portfolio-row>

          <core-portfolio-row
            :isOpened="currentlyOpened === 'contact'"
            v-on:activate="onOpenSection($event)"
            id="contact"
            colorParent="from-orange-300 to-orange-500"
            colorParent2="bg-orange-300"
            colorNameBg="bg-orange-200"
            colorNameText="text-orange-600"
            colorNameDark="text-orange-500 dark:text-orange-400"
            title="Contact me"
            iconD="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a1.994 1.994 0 01-1.414-.586m0 0L11 14h4a2 2 0 002-2V6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2v4l.586-.586z"
          >
            <h1 class="text-xl font-bold text-black dark:text-gray-50">
              Contact me if you have any questions. I will be more than happy to
              get in touch with you.
            </h1>
            <p class="mt-6 font-bold text-gray-500 dark:text-gray-500">
              <span class="mr-1">E-mail:</span>
              <a
                :href="'mailto:' + contactEmail"
                class="text-orange-400 cursor-pointer"
              >
                {{ contactEmail }}
              </a>
            </p>
            <p class="mt-2 font-bold text-gray-500 dark:text-gray-500">
              <span class="mr-1">Phone number:</span>
              <a
                :href="'tel:' + contactTelPlain"
                class="text-orange-400 cursor-pointer"
              >
                {{ constactTel }}
              </a>
            </p>

            <h1 class="mt-6 text-xl font-bold text-black dark:text-gray-50">
              One quick form stands between
              <span class="text-orange-400">you</span> and
              <span class="text-orange-400">me</span>.
            </h1>

            <form
              :action="'https://formspree.io/f/' + formSpreeKey"
              method="POST"
              class="grid grid-cols-12 gap-6 mt-6"
            >
              <input
                requiorange=""
                class="col-span-12 p-6 font-bold bg-transparent border-4 border-gray-200  dark:border-gray-600 rounded-xl md:col-span-6 focus:outline-none focus:ring-0 focus:border-orange-400"
                placeholder="Your name"
                type="text"
                name="name"
              />

              <input
                requiorange=""
                class="col-span-12 p-6 font-bold bg-transparent border-4 border-gray-200  dark:border-gray-600 rounded-xl md:col-span-6 focus:outline-none focus:ring-0 focus:border-orange-400"
                placeholder="Your e-mail"
                type="email"
                name="email"
              />

              <textarea
                requiorange=""
                style="resize: none"
                class="col-span-12 p-6 font-bold bg-transparent border-4 border-gray-200  dark:border-gray-600 rounded-xl md:col-span-12 focus:outline-none focus:ring-0 focus:border-orange-400"
                placeholder="Your message"
                rows="10"
                name="message"
              ></textarea>

              <div class="hidden col-span-6 md:block"></div>

              <button
                type="submit"
                class="col-span-12 p-6 text-xl font-bold text-white bg-orange-400 rounded-lg  md:col-span-6 hover:bg-orange-500"
              >
                Submit
              </button>
            </form>
          </core-portfolio-row>
        </div>
      </div>

      <div class="flex items-center justify-center">
        <div
          class="w-full max-w-6xl mt-4 font-bold text-center text-gray-500  dark:text-gray-500"
        >
          &copy; {{ currentYear }} Richard Nálepka,  All Rights Reserved. Template by <a href="https://www.matejbaco.eu/" class="hover:text-white">Matej Bačo.</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

declare const PhotoSwipeUI_Default: any
declare const PhotoSwipe: any

export default Vue.extend({
  data() {
    return {
      isDark: true,

      formSpreeKey: 'xeqnlgqg',
      fbUrl: 'https://www.facebook.com/profile.php?id=100006881294301',
      messengerUrl: 'https://m.me/102386341636067',
      gitHubUrl: 'https://github.com/tringug',
      discordUrl: 'https://discordapp.com/channels/@me/239373923953672192/',
      whatsappUrl: 'https://wa.me/421919178798',
      igUrl: 'https://www.instagram.com/cj.risko6g/',

      contactEmail: 'richardnalepka@gmail.com',
      constactTel: '+421 948 387 906',
      contactTelPlain: '+421948387906',

      codingSkills: [
                {
          name: 'HTML',
          level: 3,
        },
                {
          name: 'CSS',
          level: 3,
        },
                {
          name: 'MySQL',
          level: 2,
        },
        {
          name: 'PHP',
          level: 1,
        },
        {
          name: 'JavaScript',
          level: 1,
        },
      ],

      technologiesSkills: [
        {
          name: 'Windows',
          level: 3,
        },
        {
          name: 'Linux',
          level: 2,
        },
        {
          name: 'Appwrite',
          level: 2,
        },
        {
          name: 'Git',
          level: 2,
        },
        
        {
          name: 'Docker',
          level: 1,
        },
      ],

      stackItemsLeft: [
        {
          isSpecial: true,
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Appwrite</title><path d="M7.834 4C4.094 4.09.584 6.816.06 11.014a7.993 7.994 0 0 0 3.122 7.368c2.757 2.08 6.198 2.047 8.82.538a7.993 7.994 0 1 0-.005-13.834A7.84 7.84 0 0 0 7.831 4zm.122 1.485a6.525 6.526 0 0 1 6.484 5.537c0 .007.002.013.003.02.02.143.037.287.048.433l.006.054c.01.15.016.303.017.456 0 .084-.005.168-.008.252-.002.058-.003.117-.007.175a6.68 6.68 0 0 1-.03.335l-.01.08c-.015.12-.033.24-.055.358l-.01.048c-.022.124-.05.248-.08.37l-.006.025a6.578 6.58 0 0 1-.41 1.15c-.007.016-.017.033-.024.05a6.538 6.54 0 0 1-1.62 2.115l-.054.046c-.08.067-.162.13-.245.194-.055.042-.11.084-.168.125-.04.03-.08.056-.122.084a6.68 6.68 0 0 1-1.123.612 6.517 6.518 0 0 1-6.468-.8C.069 14.184.838 7.96 5.457 6.004a6.512 6.513 0 0 1 2.499-.518zm.61 3.72c-.183 0-.343.013-.352.032-.01.024-.132.504-.264 1.074-.136.57-.353 1.468-.475 2-.235.974-.377 1.613-.377 1.698 0 .023.146.042.325.042h.325l.146-.65.423-1.796c.15-.635.334-1.408.405-1.72.07-.31.14-.591.155-.624.014-.043-.066-.057-.31-.057zm-2.441 1.6-.438.47-.433.47.127.15c.07.086.264.298.428.472l.302.32h.856l-.405-.438c-.221-.235-.405-.46-.405-.49 0-.032.17-.243.377-.47.207-.23.376-.428.376-.45 0-.02-.178-.034-.395-.034zm3.27 0c-.231 0-.415.014-.415.028s.08.103.18.202c.366.367.624.678.61.74-.009.032-.188.253-.405.484l-.39.428h.437l.438-.005.4-.438c.22-.244.4-.46.4-.49 0-.023-.188-.244-.424-.493l-.423-.457z"/></svg>`,
          title: 'Appwrite',
          text: `Appwrite is extendable set of tools for developer to rapidly prepare reliable, secure, and scalable solutions.`,
        },
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Tailwind CSS icon</title><path d="M12.001,4.8c-3.2,0-5.2,1.6-6,4.8c1.2-1.6,2.6-2.2,4.2-1.8c0.913,0.228,1.565,0.89,2.288,1.624 C13.666,10.618,15.027,12,18.001,12c3.2,0,5.2-1.6,6-4.8c-1.2,1.6-2.6,2.2-4.2,1.8c-0.913-0.228-1.565-0.89-2.288-1.624 C16.337,6.182,14.976,4.8,12.001,4.8z M6.001,12c-3.2,0-5.2,1.6-6,4.8c1.2-1.6,2.6-2.2,4.2-1.8c0.913,0.228,1.565,0.89,2.288,1.624 c1.177,1.194,2.538,2.576,5.512,2.576c3.2,0,5.2-1.6,6-4.8c-1.2,1.6-2.6,2.2-4.2,1.8c-0.913-0.228-1.565-0.89-2.288-1.624 C10.337,13.382,8.976,12,6.001,12z"/></svg>`,
          title: 'Tailwind',
          text: `Tailwind is a desining framework that can be used to rapidly design and build modern websites.`,
        },
      ],

      stackItemsRight: [
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Vercel</title><path d="M24 22.525H0l12-21.05 12 21.05z"/></svg>`,
          title: 'Vercel',
          text: `Vercel let's your application go live! Vercel lets you host a website and bring content to visitors all around the world.`,
        },
        {
          iconSvg: `<svg class="w-12 h-12 text-white" fill="currentColor" fill-rule="evenodd" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Git</title><path d="M12 0c-6.626 0-12 5.372-12 12 0 6.627 5.374 12 12 12 6.627 0 12-5.373 12-12 0-6.628-5.373-12-12-12zm6.736 11.376l-6.112-6.112c-.177-.176-.408-.264-.638-.264-.231 0-.461.088-.638.264l-1.269 1.27 1.61 1.61c.375-.126.803-.042 1.102.256.299.301.384.733.254 1.109l1.551 1.551c.376-.129.809-.045 1.109.255.419.419.419 1.097 0 1.517-.419.419-1.098.419-1.518 0-.314-.316-.393-.778-.233-1.167l-1.447-1.447v3.808c.102.051.198.118.284.204.418.418.418 1.097 0 1.517-.419.419-1.099.419-1.517 0-.42-.42-.42-1.099 0-1.517.103-.104.223-.183.351-.235v-3.844c-.128-.052-.248-.13-.351-.234-.318-.317-.395-.783-.231-1.173l-1.587-1.587-4.192 4.191c-.176.177-.264.407-.264.638 0 .23.088.461.264.638l6.113 6.112c.176.176.407.263.637.263.231 0 .461-.087.638-.263l6.084-6.083c.176-.177.264-.408.264-.638 0-.231-.088-.462-.264-.638v-.001z"/></svg>`,
          title: 'Git',
          text: `Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.`,
        },
      ],

      langSkills: [
        {
          name: `Slovak`,
          level: 5,
        },
        {
          name: `Czech`,
          level: 3,
        },
        {
          name: `English`,
          level: 3,
        },
        {
          name: `Poland`,
          level: 2,
        },
      ],

      reviews: [
        {
          name: "Božena Stašenková",
          company: `Asociácia spotrebiteľských subjektov Slovenska`,
          image: '/clients/Spotreb.png',
          text: `At RAN Europe s.r.o. I received a recommendation from a friend of mine. It was a useful contact, because we are with the results of the work of RAN Europe s.r.o. and the services they provide with maximum satisfaction. Excellent communication and cooperation with this company is reflected in the end result.`,
        },

        {
          name: 'Alena Lukačovská',
          company: `Spoločenstvo vlastníkov bytov Lipa`,
          image: '/clients/Lipa.png',
          text: `Homeowners appreciate that they have better control over the activities of the homeowners' community and see transparent financial flows. RAN Europe s.r.o. prepared a suitable proposal for the publication of important information and documents. We are satisfied with the communication and services provided.`,
        },
        {
          name: 'Alena Lukačovská',
          company: `Kimchi`,
          image: '/clients/kimchi.png',
          text: ``,
        },
      ],

      projects: [
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-12'],
          mainImage: '/projects/raneurope/RAN1.png',
          name: 'RANEurope',
          description: `Simple website with basic info and contact form.`,
          images: [
            '/projects/raneurope/RAN1.png',
            '/projects/raneurope/RAN2.png',
            '/projects/raneurope/RAN3.png',
            '/projects/raneurope/RAN4.png',
            '/projects/raneurope/RAN5.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/kimchi/kimchi1.png',
          name: 'Kimchi',
          description: `Kimchi company website presentation.`,
          images: [
            '/projects/kimchi/kimchi1.png',
            '/projects/kimchi/kimchi2.png',
            '/projects/kimchi/kimchi3.png',
            '/projects/kimchi/kimchi4.png',
            '/projects/kimchi/kimchi5.png',
            '/projects/kimchi/kimchi6.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-8'],
          mainImage: '/projects/authmodal/A-1.png',
          name: 'Auth Modal',
          description: `Simple template for login register...`,
          images: [
            '/projects/authmodal/A-1.png',
            '/projects/authmodal/A-2.png',
            '/projects/authmodal/A-3.png',
            '/projects/authmodal/A-4.png',
            '/projects/authmodal/A-5.png',
            '/projects/authmodal/A-6.png',
          ],
        },

        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-8'],
          mainImage: '/projects/spotrebitel/spot1.png',
          name: 'Asociácia spotrebiteľských subjektov slovenska',
          description: `Representation website.`,
          images: [
            '/projects/spotrebitel/spot1.png',
            '/projects/spotrebitel/spot2.png',
            '/projects/spotrebitel/spot3.png',
            '/projects/spotrebitel/spot4.png',
          ],
        },
        {
          grid: ['col-span-12 md:col-span-6 lg:col-span-4'],
          mainImage: '/projects/rensk/rensk1.png',
          name: 'SVB Lipa',
          description: `Basic website with blog section and document section.`,
          images: [
            '/projects/lipa/lipa1.png',
            '/projects/lipa/lipa2.png',
            '/projects/lipa/lipa3.png',
          ],
        },
      ],

      currentlyOpened: 'none',
      iframe: null as any,
      currentYear: new Date().getFullYear(),

      currentColor: 'from-green-300 to-green-500',
      // from-{{ currentColor }}-300 to-{{ currentColor }}-500

      currentColor2: 'bg-green-300',
      // bg-{{ currentColor }}-300
    }
  },
  methods: {
    onToggleDar() {
      this.isDark = !this.isDark
      this.syncDarkness()
    },
    onDownloadCV() {
      const link = document.createElement('a')
      link.download = 'CV_Richard_Nalepka.pdf'
      link.href = '/CV_Richard_Nalepka.pdf'

      document.body.appendChild(link)
      link.click()

      document.body.removeChild(link)
    },

    onPrintCV() {
      if (this.iframe) {
        if (this.iframe.contentWindow) {
          this.iframe.focus()
          this.iframe.contentWindow.print()
        }
        return
      }

      this.iframe = document.createElement('iframe')
      document.body.appendChild(this.iframe)

      this.iframe.style.display = 'none'
      this.iframe.onload = () => {
        setTimeout(() => {
          if (this.iframe.contentWindow) {
            this.iframe.focus()
            this.iframe.contentWindow.print()
          }
        }, 300)
      }

      this.iframe.src = '/CV_Richard_Nalepka.pdf'
    },

    goTo(url: string) {
      window.location.href = url
    },

    scroll(el: any) {
      const dateStart = Date.now()

      let i = 0
      const step = (wrapper: any, i: number) => {
        if (i > 60 || Math.abs(dateStart - Date.now()) > 600) {
          return
        }

        const destinationPos = el.offsetTop - 15
        const currentPos = wrapper.scrollTop

        let stepLength = Math.max(
          20,
          Math.abs(currentPos - destinationPos) * 0.2
        )

        if (Math.abs(currentPos - destinationPos) < 500) {
          stepLength = 20
        }

        let newPos
        if (currentPos > destinationPos) {
          newPos = currentPos - stepLength

          if (newPos < destinationPos) {
            newPos = destinationPos
          }
        } else {
          newPos = currentPos + stepLength

          if (newPos > destinationPos) {
            newPos = destinationPos
          }
        }

        wrapper.scrollTo(null, newPos)

        setTimeout(() => {
          step(wrapper, i + 1)
        }, 10)
      }

      const wrapper: any = document.querySelector('#page_wrapper')
      if (el && wrapper) {
        step(wrapper, 0)
      }
    },

    checkVisible(elm: any) {
      return false
      // var rect = elm.getBoundingClientRect();
      // var viewHeight = Math.max(
      //   document.documentElement.clientHeight,
      //   window.innerHeight
      // );
      // return !(rect.bottom < 0 || rect.top - viewHeight >= 0);
    },

    onOpenSection(event: { color: string; color2: string; id: string }) {
      if (this.currentlyOpened === event.id) {
        this.currentlyOpened = 'none'
        this.currentColor = 'from-green-300 to-green-500'
        this.currentColor2 = 'bg-green-300'

        const selector: any = document.querySelector('#intro')
        // this.scroll(selector)

        return
      }

      this.currentColor = event.color
      this.currentColor2 = event.color2
      this.currentlyOpened = event.id

      const selector: any = document.querySelector('#' + event.id)
      // this.scroll(selector)
    },

    onOpenGallery(projectIndex: number) {
      const project = this.projects[projectIndex]
      const pswpElement = document.querySelector('.pswp')

      const items = project.images.map((img) => {
        return {
          src: img,
          w: 1920,
          h: 1200,
        }
      })
      console.log(items)

      const options = {
        index: 0,
      }

      const gallery = new PhotoSwipe(
        pswpElement,
        PhotoSwipeUI_Default,
        items,
        options
      )
      gallery.init()
    },
    syncDarkness() {
      if (this.isDark) {
        document.body.classList.add('dark')
      } else {
        document.body.classList.remove('dark')
      }
    },
  },
  created() {
    this.syncDarkness()
  },
})
</script>
