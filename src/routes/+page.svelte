<script lang="ts">
    import { Button } from "$lib/components/ui/button";
    import * as Avatar from "$lib/components/ui/avatar/index.js";
    
    import { Tabs } from "$lib/components/ui/tabs";
    import { Card } from "$lib/components/ui/card";
    import { Label } from "$lib/components/ui/label";
    import { Switch } from "$lib/components/ui/switch";
    import { Menubar } from "$lib/components/ui/menubar";

    import { goto } from '$app/navigation';

    import { onMount } from 'svelte';

    // Dummy data for the user profile
    let userProfile = {
        name: 'John Doe',
        profilePhoto: 'path/to/profile-photo.jpg',
        bio: 'Passionate about coding and design...',
        isFollowing: false,
        companyName: 'Tech Co.',
        position: 'Software Engineer',
        website: 'https://example.com',
    };

    // Function to handle follow button click
    function toggleFollow() {
        userProfile.isFollowing = !userProfile.isFollowing;
    }
    let followed = false;

    function follow() {
        followed = !followed;
    }

  </script>
   
   <nav class="bg-white">
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-between py-4 border-b border-dotted">
        <!-- Logo -->
        <div class="flex items-center">
          <Button class="navbar-buttons">
            <a href="/home" class=" flex">
                <img src="logo_icon.png" alt="duggup Logo" class="h-8 w-auto" />
                <span class="ml-2 text-black font-semibold">duggup</span>
            </a>
        </Button>
        </div>
  

  
        
        <div class="flex items-center space-x-6">
            <!-- Navigation Links -->
            <div class="hidden md:flex space-x-8">
                <a href="/home" class="text-black hover:text-gray-600">Home</a>
                <a href="/explore" class="text-black hover:text-gray-600">Explore</a>
                <a href="/learn" class="text-black hover:text-gray-600">Learn</a>
                <a href="/new-post" class="text-black hover:text-gray-600">+Post</a>
            </div>
            <!-- User Profile -->
          <a href="/" class="flex items-center space-x-4">
            <img src="/Krishna-img.png" alt="User Avatar" class="h-8 w-8 rounded-full" />
            <span class="text-black font-semibold">Krishna Kiran</span>
          </a>
          <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5 text-gray-600 cursor-pointer"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M10 2a8 8 0 100 16 8 8 0 000-16zM8 11a1 1 0 011-1h2a1 1 0 110 2H9a1 1 0 01-1-1zm0-4a1 1 0 011-1h2a1 1 0 110 2H9a1 1 0 01-1-1z"
            clip-rule="evenodd"
          />
        </svg>
        </div>
      </div>
    </div>
  </nav>
  
  <div class="top-bar flex w-full md:w-8/12 mx-auto mt-4 ">
    <div class="profile-details text-center mb-0">
        <img src="/Krishna-img.png" alt="Krishna Kiran" class="mx-auto w-30 h-30 rounded-full border-4 border-white" />
        <div class="text-gray-600 mt-2">Krishna <br /> Kiran </div>
      </div>
      
      <div class="bio text-center flex flex-col items-center">
        <p class="mb-2">Co-Founder and CEO at Duggup - Social network for people in tech. Ex-Amazon Head of Engineering. I write hot-takes on building a business, shipping delightful products and accelerating product and career growth.</p>
        <button class="follow-btn px-4 py-2 border border-gray-300 {followed ? 'bg-white-500 text-grey' : 'bg-white text-black'} mt-2" on:click={follow}>
          {followed ? 'Following' : 'Follow'}
        </button>
      </div>
      
    <div class="company-details text-center">
      <img src="/Duggup-logo.png" alt="Company Logo" class="mx-auto mb-2 w-6 h-auto" />
      <p class="mb-9 h-auto">Duggup</p>
      <a href="#" class="text-grey-500">My Website</a>
    </div>
  </div>
  



  <div class="container w-8/12 flex-col bg-blend-color-burn p-4 ml-4">
    <div class="section1">

        <!-- Component 3: Timeline Job Stories -->
        <div class="story flex h-48 rounded-md">
          <!-- Content goes here -->
          <div class="flex flex-row-reverse relative w-52">
              <img src="/dotted-line.png" alt="img" class="h-full"/>
              <div class="relative top-1/2 text-grey-500 text-xs right-4">
                  <p>Dec 2023</p>
                </div>
          </div>
          <div class="flex justify-evenly relative">
              <div class="flex-col justify-center w-72">
                  <img src="story1.png" alt="Story 1" class="w-72 h-auto p-2" />
                  <p class="text-xs justify-center">No amount of technology can convert a bad story into a good story.</p>
              </div>
              <div class="flex-col justify-center w-72">
                  <img src="story2.png" alt="Story 1" class="w-72 h-auto p-2" />
                  <p class="text-xs justify-center">Most people don't have original ideas. Here is how Sam Altman pushes himself to have unpopular ideas.</p>
              </div>
      
          </div>
  
        </div>
  
          <!-- Component 2: Job Description -->
        <div class="description story flex  h-20 rounded-md">
          <!-- Content goes here -->
          <div class="profile-card relative flex text-right ">
              <img src="arrow.png" class=" relative h-full right-1.5"/>
              <div class="relative text-right right-5 ">
                  <img src="/Duggup-logo.png" alt="Company Logo" class="logo ml-auto" />
                <h2 class="text-sm font-bold text-blue-500 ">Duggup</h2>
                <p class="text-xs text-gray-500">San Francisco Bay Area</p>
                <p class="text-xs/[5px] text-gray-400">Joined Nov 2023</p>
              </div>
              
            </div>
  
            <div class="p-4">
              <p class="font-bold text-gray-600">Co-Founder and CEO</p>
              <p class="text-xs text-gray-500">Full time - Remote</p>
      
            </div>
  
        </div>
        
        
      
  
      
    </div>
  
    <div class="section2">

      <!-- Component 3: Timeline Job Stories -->
      <div class="story flex h-48 rounded-md ">
        <!-- Content goes here -->
        <div class="flex flex-row-reverse relative w-52">
            <img src="/dotted-line.png" alt="img" class="h-full"/>
            <div class="relative top-1/2 text-grey-500 text-xs right-4">
                <p>Nov 2023</p>
              </div>
        </div>
        <div class="flex justify-evenly relative">
            <div class="flex-col justify-center w-72">
                <img src="story21.png" alt="Story 1" class="w-72 h-auto p-2" />
                <p class="text-xs justify-center">Startup Lesson I am reflecting. Don't build for the "average person".</p>
            </div>
            <div class="flex-col justify-center w-72">
                <img src="story22.png" alt="Story 1" class="w-72 h-auto p-2" />
                <p class="text-xs justify-center">Your biggest regrets at 80 will be acts of omission.</p>
            </div>
    
        </div>

      </div>

        <!-- Component 2: Job Description -->
      <div class="description story flex h-20 rounded-md mb-4">
        <!-- Content goes here -->
        <div class="profile-card relative flex text-right ">
            <img src="arrow.png" class=" relative h-full right-1.5 "/>
            <div class="relative text-right right-5 ">
                <img src="/Betterup-logo.png" alt="Company Logo" class="logo ml-auto" />
              <h2 class="text-sm font-bold text-blue-500 ">Betterup</h2>
              <p class="text-xs text-gray-500">San Francisco Bay Area</p>
              <p class="text-xs/[5px] text-gray-400">Joined Jan 2023</p>
            </div>
            
          </div>

          <div class="p-4">
            <p class="font-bold text-gray-600">VP- Engineering</p>
            <p class="text-xs text-gray-500">Full time</p>
    
          </div>

      </div>
      
      
    </div>
  </div>
  

  <style global lang="pcss">
    
    .border-dotted {
      border-bottom: 1px dotted #ccc;
    }

    .follow-btn:hover {
        background-color: blue;
        color: white;
      }

      .profile-card {
        @apply rounded-md flex-row-reverse relative w-52;
      }
    
      .logo {
        @apply w-4 h-4 rounded-full;
      }
      .top-bar{
        @apply justify-center left-72 right-9
      }
      

  </style>