# Basic Full Star Rating in Vue

Basic Star-Rating component for Vue project.
## Look (adjustable)
![Rating](/src/assets/Capture1.PNG)

![Rating](/src/assets/Capture2.PNG)

![Rating](/src/assets/Capture.PNG)

## Project setup
```
Stars are unicode character (&#9733), does not require any setup in existing vue project.
If stars switched to font icons (like font-awesome), import of subject font will required.
```

### Component code
```
  <template>
  <div class="star-rate">
    <span
      :class="{ checked: rating > 0 || mouseOver > 0 }"
      @mouseover="mouseOver = 1"
      @mouseleave="mouseOver = 0"
      @click="AddEditRate(1)"
      >&#9733;</span>
    <span
      :class="{ checked: rating > 1 || mouseOver > 1 }"
      @mouseover="mouseOver = 2"
      @mouseleave="mouseOver = 0"
      @click="AddEditRate(2)"
      >&#9733;</span>
    <span
      :class="{ checked: rating > 2 || mouseOver > 2 }"
      @mouseover="mouseOver = 3"
      @mouseleave="mouseOver = 0"
      @click="AddEditRate(3)"
      >&#9733;</span>
    <span
      :class="{ checked: rating > 3 || mouseOver > 3 }"
      @mouseover="mouseOver = 4"
      @mouseleave="mouseOver = 0"
      @click="AddEditRate(4)"
      >&#9733;</span>
    <span
      :class="{ checked: rating > 4 || mouseOver > 4 }"
      @mouseover="mouseOver = 5"
      @mouseleave="mouseOver = 0"
      @click="AddEditRate(5)"
      >&#9733;</span>
    <p>{{ rating > 0 ? `You rated ${rating}` : "Rate?" }}</p>
  </div>
</template>

<script>

export default {
  props: ["existingRating"],

  data() {
    return {
      rating: 0,
      mouseOver: 0,
    };
  },
  created() {
    this.findUserRate();
  },
  methods: {
    findUserRate() {
     this.rating= this.existingRating;
      
    },
    AddEditRate(rate) {
      // Your add - edit function here 
      this.rating =rate; /*store clicked rating*/
    },
  },
};
</script>
```

### Styles
```
<style >
.star-rate {
  /* adjust star size */
  font-size: 20pt; 
}
div p {
  font-size: 7pt;
  color: black;
  font-style: italic;
  margin-bottom: 0px;
}
.checked {
  color: gold;
}
div span {
  color: rgb(196, 193, 193);
}
div span:hover {
  -webkit-filter: drop-shadow(5px 5px 5px rgba(34, 34, 34, 0.904));
  filter: drop-shadow(5px 5px 5px rgba(34, 34, 34, 0.904));
  color: gold;
}

</style>
```


###  Pass existing rating as prop from other component or view
```
<star-rating :existingRating="0"/> 
```
