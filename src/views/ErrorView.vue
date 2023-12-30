<template>
    <div class="home">        
        <h1>Page not Found</h1>
    </div>
    </template>
    
    <style scoped>
    .home{
        display: flex;
        align-items: center;
        justify-content:center;
    }
    
    h1{
        font-size: 80px;
        color:rgb(177, 32, 32);
        animation: bounce 1.5s infinite;
    }
      
      @keyframes bounce {
        0%, 20%, 50%, 80%, 100% {
          transform: translateY(0);
        }
        40% {
          transform: translateY(-30px);
        }
        60% {
          transform: translateY(-15px);
        }
      }
    </style>