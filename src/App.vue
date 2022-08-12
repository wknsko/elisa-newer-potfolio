<template>
  <header>
    <div class="title">
      <h1>Elisa Newer Photography</h1>
    </div>
  </header>

  <div class="container">
    <div class="container-item">
      <div @click="clickMenu(1)" class="container-title">
        <h2>Meet me</h2>
      </div>
      <transition :name="animation">
        <div id="slide1" class="container-body" v-if="show === 1">
          <div class="hello">
            <div class="column-one">
              <img src="./assets/meetme.jpeg" alt="">
            </div>
            <div class="column-two">
              <div class="first-row">Hello!</div>
              <div class="second-row">I'm a photographer based in Seattle</div>
              <div class="third-row">
                <div class="line"></div>
                <div class="text">Book me for your event</div>
              </div>
              <div class="about">
                <p>
                  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eaque, reiciendis dolores. Excepturi dolores
                  praesentium unde accusantium magni, aspernatur aliquid harum, incidunt asperiores, sequi facere fugit.
                  Unde similique alias incidunt asperiores!
                </p>
                <p>
                  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quam voluptatum, esse facilis impedit culpa
                  mollitia?
                </p>
              </div>
            </div>
          </div>
        </div>
      </transition>
    </div>

    <div class="container-item">
      <div @click="clickMenu(2)" class="container-title">
        <h2>Events</h2>
      </div>
      <transition name="next">
        <div id="slide2" class="container-body examples" v-if="show === 2">

          <div class="weddings">
            <h4>Weddings</h4>
            <div class="slider">
              <div class="arr-left">&lt;</div>
              <img src="./assets/couples1.jpeg" alt="">
              <div @class=" next(idx[0]++)" class="arr-right">&gt;
            </div>
          </div>
        </div>

        <div class="couples">
          <h4>Couples</h4>
          <div class="slider">
            <div class="arr-left">&lt;</div>
            <img src="./assets/couples1.jpeg" alt="">
            <div class="arr-right">&gt;</div>
          </div>
        </div>

        <div class="celebration">
          <h4>Celebrations</h4>
          <div class="slider">
            <div class="arr-left">&lt;</div>
            <img src="./assets/wedding1.jpeg" alt="">
            <div class="arr-right">&gt;</div>
          </div>
        </div>

    </div>
    </transition>
  </div>

  <div class="container-item">

    <div @click="clickMenu(3)" class="container-title">
      <h2>Contact</h2>
    </div>
    <transition name="next">

      <div id="slide3" class="container-body" v-if="show === 3">
        <form action=" " class="form">
          <div class="column-one">
            <input type="text" placeholder="Full Name" />
            <input type="text" placeholder="Email" />
            <input type="number" name="" id="" placeholder="Phone">
          </div>
          <div class="column-two">
            <input type="text" placeholder="Type of Event" />
            <input type="date" name="" id="" placeholder="Date of Event">
            <input type="text" placeholder="Location of Event" />
          </div>
          <div class="message">
            <label for="message">Tell me more!</label>
            <textarea name="message" id="message" cols="30" rows="10"></textarea>
          </div>
          <button class="btn-submit">Submit</button>
        </form>
      </div>
    </transition>

  </div>

  </div>
</template>

<script>




export default {
  name: 'App',
  data() {
    return {
      show: 2,
      back: false,
      animation: '',
      photos: [
        ['wedding1.jpeg', 'wedding1.jpeg', 'wedding1.jpeg', 'wedding1.jpeg']
      ]
      
      
    }
  },
  methods: {
    clickMenu(idx){
      if(idx < this.show){
        console.log(idx, typeof idx)
        this.animation = 'prev'
        setTimeout(() => {
          this.show = idx;
        },1000)
        
        
      } else {
        this.animation = 'next'
        this.show = idx;
      }
    },
   
    
  },
  components: {
    
  }
}
</script>

<style>

.next-enter-from {
  transform: translate(0, 0);
  opacity: 0;
}
.next-enter-to {
  transform: translate(-100%, 0);
  opacity: 0.8;
}

.next-leave-active,
.next-enter-active {
  transition: 3s;
}

.next-leave-from {
  transform: translate(0, 0);
  opacity: 0;
}

.next-leave-to {
  transform: translate(-100%, 0);
  opacity: 0;
}

.prev-enter-from {
  transform: translate(-100%, 0);
  opacity: 0;
}

.prev-enter-to {
  transform: translate(0, 0);
  opacity: 0.8;
}

.prev-leave-active,
.prev-enter-active {
  transition: 3s;
}

.prev-leave-from {
  transform: translate(-100%, 0);
  opacity: 0.8;
}

.prev-leave-to {
  transform: translate(100%, 0);
  opacity: 0;
}




</style>
