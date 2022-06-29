<template>
  <div class="fontView">
      <div class="fontView__header">
        <select class="select" v-model="familySelected" @change="familyChange">
          <option v-for="faimly in fontFamily" :value="faimly.text" :key="faimly.id">{{ faimly.text }}</option>
        </select>

        <select class="select" v-model="weightSelected" @change="weightChange">
          <option v-for="weight in fontWeight" :value="weight.number" :key="weight.number">{{ weight.name }}</option>
        </select>

        <div class="form">
          <div class="form__inputWrap">
            <input type="radio" name="lang" id="KR" value="KR" v-model="lang" @change="langChange" checked>
            <label for="KR">KR</label>
          </div>
          <div class="form__inputWrap">
            <input type="radio" name="lang" id="EN" value="EN" v-model="lang" @change="langChange">
            <label for="EN">EN</label>
          </div>
        </div>
      </div>
      
      <ul class="fontView__list">
        <li class="fontView__item" v-for="item in fontItems" :key="item.fontSize">
          <span class="fontView__sizeText" :style="{ fontFamily: item.fontFamily }">{{ item.fontSize }}</span>
          <p class="fontView__itemText" :style="item">{{ krText }}</p>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  data() {
    return {
      lang: 'KR',
      krText: '따뜻한 같이, 이상은 교향악이다. 인류의 못할 이것은 어디 속잎나고, 불러 피다. 투명하되 얼음 인도하겠다는 모래뿐일 교향악이다. 대한 같은 없으면, 있으랴? 수 갑 하였으며, 가지에 사랑의 없으면 운다. 눈에 그들은 청춘이 칼이다. 힘차게 뜨거운지라, 현저하게 쓸쓸하랴? 노래하며 무엇을 때까지 사막이다. 역사를 대고, 있을 심장의 커다란 공자는 것이다. 못할 노년에게서 피고, 이성은 웅대한 두손을 약동하다. 행복스럽고 동산에는 끓는 구하지 피고, 이 인간의 싸인 이것이다. 생명을 주는 얼음에 목숨을 보라. 가치를 사랑의 얼마나 인간은 바이며, 풍부하게 그들은 하여도 아니다. 인도하겠다는 바로 봄바람을 끓는 보이는 무한한 트고, 뜨거운지라, 위하여 교향악이다. 곳이 이는 하는 광야에서 물방아 인간은 과실이 간에 그들의 부패뿐이다. 방황하였으며, 못하다 우리 이 청춘의 위하여 주며, 피는 그리하였는가? 인간은 들어 밥을 생생하며, 끓는 용감하고 생명을 청춘의 때문이다. 대중을 할지니, 구하지 구하기 뜨거운지라, 인도하겠다는 품으며, 위하여서. 무한한 새가 힘차게 목숨을 들어 말이다. 무엇을 맺어, 청춘의 꽃이 발휘하기 거친 인간의 어디 칼이다. 피가 없으면 이상의 보이는 않는 얼마나 쓸쓸한 설산에서 기쁘며, 뿐이다. 청춘을 많이 평화스러운 스며들어 몸이 사막이다. 인간에 위하여서 가슴이 길지 인간의 것이다. 천자만홍이 무엇을 지혜는 그것을 사라지지 얼음 청춘 뜨거운지라, 현저하게 있으랴? 사라지지 굳세게 밥을 위하여서 물방아 생생하며, 얼음에 만천하의 꽃이 피다. 천자만홍이 풍부하게 얼음에 운다. 어디 인간의 무엇을 오직 튼튼하며, 위하여서 이상의 구할 커다란 사막이다. 우리는 무엇을 현저하게 말이다. 얼음 위하여 예가 새가 가진 긴지라 우리는 같으며, 이것이다. 거선의 기쁘며, 그림자는 봄바람이다.',
      enText: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ullam ipsum assumenda cum iste, nisi aliquam at odit asperiores. Suscipit assumenda veritatis corrupti nisi molestias ex cumque quidem, voluptatum officia nam.',
      familySelected: 'Noto Sans KR',
      weightSelected: '400',
      fontFamily: [
        {
          id: 1,
          text: 'Noto Sans KR',
        },
        {
          id: 2,
          text: 'Pretendard',
        }
      ],
      fontWeight: [
        {
          name: 'Light',
          number: '300',
        },
        {
          name: 'Regular',
          number: '400',
        },
        {
          name: 'Medium',
          number: '500',
        },
        {
          name: 'Semi-Bold',
          number: '600',
        },
        {
          name: 'Bold',
          number: '700',
        },
        {
          name: 'Extra-Bold',
          number: '800',
        },
        {
          name: 'Black',
          number: '900',
        }
      ],
      fontItems: [
        {
          fontSize: '28px',
          lineHeight: 1.43,
        },
        {
          fontSize: '24px',
          lineHeight: 1.16,
        },
        {
          fontSize: '20px',
          lineHeight: 1.6,
        },
        {
          fontSize: '18px',
          lineHeight: 1.33,
        },
        {
          fontSize: '16px',
          lineHeight: 1.37,
        },
        {
          fontSize: '14px',
          lineHeight: 1.42,
        },
        {
          fontSize: '13px',
          lineHeight: 1.38,
        },
        {
          fontSize: '11px',
          lineHeight: 1.63,
        }
      ]
    }
  },
  methods: {
    // language 변경
    langChange() {
      if (this.lang === 'KR') {
        document.querySelectorAll('.fontView__itemText').forEach(el => {
          el.innerText = `${this.krText}`;
        });
      } else if (this.lang === 'EN') {
        document.querySelectorAll('.fontView__itemText').forEach(el => {
          el.innerText = `${this.enText}`;
        });
      }
    },
    // font-family 변경
    familyChange() {
      this.fontItems.forEach(style => {
        style.fontFamily = this.familySelected;
      });
    },
    // font-weight 변경
    weightChange() {
      this.fontItems.forEach(style => {
        style.fontWeight = this.weightSelected;
      });
    }
  }
}
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100;300;400;500;700;900&display=swap');

  @font-face {
    font-family: "Pretendard";
    font-weight: 900;
    font-display: swap;
    src: local("Pretendard Black"),
        url("../assets/fonts/pretendard/Pretendard-Black.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 800;
    font-display: swap;
    src: local("Pretendard ExtraBold"),
        url("../assets/fonts/pretendard/Pretendard-ExtraBold.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 700;
    font-display: swap;
    src: local("Pretendard Bold"),
        url("../assets/fonts/pretendard/Pretendard-Bold.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 600;
    font-display: swap;
    src: local("Pretendard SemiBold"),
        url("../assets/fonts/pretendard/Pretendard-SemiBold.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 500;
    font-display: swap;
    src: local("Pretendard Medium"),
        url("../assets/fonts/pretendard/Pretendard-Medium.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 400;
    font-display: swap;
    src: local("Pretendard Regular"),
        url("../assets/fonts/pretendard/Pretendard-Regular.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 300;
    font-display: swap;
    src: local("Pretendard Light"),
        url("../assets/fonts/pretendard/Pretendard-Light.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 200;
    font-display: swap;
    src: local("Pretendard ExtraLight"),
        url("../assets/fonts/pretendard/Pretendard-ExtraLight.woff2") format("woff2");
  }

  @font-face {
    font-family: "Pretendard";
    font-weight: 100;
    font-display: swap;
    src: local("Pretendard Thin"),
        url("../assets/fonts/pretendard/Pretendard-Thin.woff2") format("woff2");
  }

  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  p {
    margin: 0;
    font-weight: 400;
  }

  .fontView__header {
    padding: 20px;
    background-color: #FAFAFA;
  }

  .fontView__list {
    padding: 40px 20px;
  }

  .fontView__item:not(:first-child) {
    margin-top: 40px;
  }
  
  .fontView__itemText {
    display: -webkit-box;
    overflow: hidden;
    word-break: break-all;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    font-family: 'Noto Sans KR';
    font-weight: 400;
  }

  .fontView__sizeText {
    display: block;
    font-family: 'Noto Sans KR';
    font-weight: 400;
    font-size: 14px;
    line-height: 1.42;
  }
</style>