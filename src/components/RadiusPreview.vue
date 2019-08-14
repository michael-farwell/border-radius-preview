<template>
    <div>
        <b-row>
            <b-col>
                <div class="box-user" :style="userBorders">
                    <h2 class="text-center">Border Radius Values</h2>
                    <b-form>
                        <b-row>
                            <b-col>
                                <b-form-group label="Top Left X"
                                              label-for="topLeftX">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="topLeftX"
                                                  v-model="topLeftX">
                                    </b-form-input>
                                </b-form-group>
                                &nbsp;
                                <b-form-group label="Top Left Y"
                                              label-for="topLeftY">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="topLeftY"
                                                  v-model="topLeftY">
                                    </b-form-input>
                                </b-form-group>
                            </b-col>
                        </b-row>
                        <b-row>
                            <b-col>
                                <b-form-group label="Top Right X"
                                              label-for="topRightX">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="topRightX"
                                                  v-model="topRightX">
                                    </b-form-input>
                                </b-form-group>
                                &nbsp;
                                <b-form-group label="Top Right Y"
                                              label-for="topRightY">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="topRightY"
                                                  v-model="topRightY">
                                    </b-form-input>
                                </b-form-group>
                            </b-col>
                        </b-row>
                        <b-row>
                            <b-col>
                                <b-form-group label="Bottom Right X"
                                              label-for="bottomRightX">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="bottomRightX"
                                                  v-model="bottomRightX">
                                    </b-form-input>
                                </b-form-group>
                                &nbsp;
                                <b-form-group label="Bottom Right Y"
                                              label-for="bottomRightY">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="bottomRightY"
                                                  v-model="bottomRightY">
                                    </b-form-input>
                                </b-form-group>
                            </b-col>
                        </b-row>
                        <b-row>
                            <b-col>
                                <b-form-group label="Bottom Left X"
                                              label-for="bottomLeftX">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="bottomLeftX"
                                                  v-model="bottomLeftX">
                                    </b-form-input>
                                </b-form-group>
                                &nbsp;
                                <b-form-group label="Bottom Left Y"
                                              label-for="bottomLeftY">
                                    <b-form-input type="number"
                                                  max="100"
                                                  min="0"
                                                  id="bottomLeftY"
                                                  v-model="bottomLeftY">
                                    </b-form-input>
                                </b-form-group>
                            </b-col>
                        </b-row>
                    </b-form>
                </div>
            </b-col>
        </b-row>
        <b-row class="mt-3">
            <b-col>
                <div>
                    <h2 class="text-center">CSS</h2>
                    <blockquote>
                        <code>border-radius: {{userBorders['border-radius']}}</code>
                    </blockquote>
                    <b-button @click="copyStyle">Copy</b-button>
                </div>
            </b-col>
        </b-row>
    </div>
</template>

<script>
  export default {
    data() {
      return {
        topLeftX: 0,
        topLeftY: 100,
        topRightX: 0,
        topRightY: 100,
        bottomRightX: 0,
        bottomRightY: 100,
        bottomLeftX: 100,
        bottomLeftY: 0,
        userBorders: {
          'border-radius': '0% 100% 0% 100% / 100% 0% 100% 0%',
        },
      };
    },
    watch: {
      topLeftX() {
        this.topLeftX = this.checkValue(this.topLeftX);

        this.topLeftY = 100 - this.topLeftX;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      topLeftY() {
        this.topLeftY = this.checkValue(this.topLeftY);

        this.topLeftX = 100 - this.topLeftY;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      topRightX() {
        this.topRightX = this.checkValue(this.topRightX);

        this.topRightY = 100 - this.topRightX;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      topRightY() {
        this.topRightY = this.checkValue(this.topRightY);

        this.topRightX = 100 - this.topRightY;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      bottomRightX() {
        this.bottomRightX = this.checkValue(this.bottomRightX);

        this.bottomRightY = 100 - this.bottomRightX;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      bottomRightY() {
        this.bottomRightY = this.checkValue(this.bottomRightY);

        this.bottomRightX = 100 - this.bottomRightY;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      bottomLeftX() {
        this.bottomLeftX = this.checkValue(this.topLeftX);

        this.bottomLeftY = 100 - this.bottomLeftX;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
      bottomLeftY() {
        this.bottomLeftY = this.checkValue(this.bottomLeftY);

        this.bottomLeftX = 100 - this.bottomLeftY;
        this.userBorders['border-radius'] = `${this.topLeftX}% `;
        this.userBorders['border-radius'] += `${this.topLeftY}% `;
        this.userBorders['border-radius'] += `${this.bottomRightX}% `;
        this.userBorders['border-radius'] += `${this.bottomRightY}% / `;
        this.userBorders['border-radius'] += `${this.bottomLeftX}% `;
        this.userBorders['border-radius'] += `${this.topRightX}% `;
        this.userBorders['border-radius'] += `${this.topRightY}% `;
        this.userBorders['border-radius'] += `${this.bottomLeftY}%`;
      },
    },
    methods: {
      checkValue(num) {
        if (num > 100) {
          return 100;
        } else if (num < 0) {
          return 0;
        } else {
          return num;
        }
      },
      copyStyle() {
        this.$clipboard(`border-radius: ${this.userBorders['border-radius']}`);
        alert('Copied to clipboard');
      },
    },
  };
</script>

<style scoped>
    .col {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .box-user {
        border: 1px solid black;
        height: 100%;
        width: 100%;
        padding-top: 100px;
        padding-bottom: 100px;
    }
</style>
