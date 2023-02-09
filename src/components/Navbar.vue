<template>
    <nav class="px-2 sm:px-4 py-2.5 bg-gray-900 w-full z-20 top-0 left-0">
        <div class="container flex flex-wrap items-center justify-between mx-auto">
            <a href="/home" class="flex items-center">
                <img src="https://i.pinimg.com/564x/1f/17/73/1f177370ba22481e0e5068e9db6374f9.jpg" class="h-10 rounded mr-3" alt="Flowbite Logo">
                <span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">Review Resto</span>
            </a>
            <div class="flex md:order-2">
                <button type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-3 md:mr-0 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Get started</button>
            </div>

            <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1">
                <ul class="flex flex-col p-4 mt-4 rounded-lg lg:flex-row space-x-8 mt-0">
                <li>
                    <a href="#" class="block py-2 pl-3 pr-4 text-white p-0 font-['Montserrat']" aria-current="page">Home</a>
                </li>
                <li>
                      <a href="#" class="block py-2 pl-3 pr-4 text-gray-400 p-0 font-['Montserrat'] hover:text-white">About</a>
                </li>
                <li>
                    <a href="#" class="block py-2 pl-3 pr-4 text-gray-400  p-0 font-['Montserrat'] hover:text-white">Services</a>
                </li>
                <li>
                    <a href="#" class="block py-2 pl-3 pr-4 text-gray-400  p-0 font-['Montserrat'] hover:text-white">Contact</a>
                </li>
                </ul>
            </div>
        </div>
    </nav>
</template>
