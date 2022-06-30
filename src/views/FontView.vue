<template>
  <div class="fontView">
    <div class="fontView__header">
      <div class="fontView__selectWrap">
        <label class="fontView__selectLabel" for="Font">서체</label>
        <select id="Font" class="formSelect" v-model="familySelected" @change="familyChange">
          <option v-for="faimly in fontFamily" :value="faimly.text" :key="faimly.id">{{ faimly.text }}</option>
        </select>
      </div>
      
      <div class="fontView__selectWrap">
        <label class="fontView__selectLabel" for="Weight">굵기</label>
        <select id="Weight" class="formSelect" v-model="weightSelected" @change="weightChange">
          <option v-for="weight in fontWeight" :value="weight.number" :key="weight.number">{{ weight.name }}</option>
        </select>
      </div>

      

      <div class="formChecks">
        <div class="formCheck">
          <input class="formCheck__input" type="radio" name="lang" id="KR" value="KR" v-model="lang" @change="langChange" checked>
          <label class="formCheck__label" for="KR">KR</label>
        </div>
        <div class="formCheck">
          <input class="formCheck__input" type="radio" name="lang" id="EN" value="EN" v-model="lang" @change="langChange">
          <label class="formCheck__label" for="EN">EN</label>
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
      breakPoint: 768,
      breakCheck: '',
      familySelected: 'Pretendard',
      weightSelected: '400',
      fontFamily: [
        {
          id: 1,
          text: 'Pretendard',
        },
        {
          id: 2,
          text: 'Noto Sans KR',
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
  mounted() {
    window.addEventListener('resize', this.handleResize);
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
    },
    // breakPoint 체크
    handleResize() {
      window.outerWidth >= this.breakPoint ? this.breakCheck = true : this.breakCheck = false;
    }
  }
}
</script>

<style lang="scss" scoped>
  p {
    margin: 0;
    font-weight: 400;
  }

  .fontView__header {
    display: flex;
    flex-wrap: wrap;
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
    font-family: 'Pretendard';
    font-weight: 400;
  }

  .fontView__sizeText {
    display: block;
    font-family: 'Noto Sans KR';
    font-weight: 400;
    line-height: 1.42;
  }

  .fontView__selectWrap {
    display: flex;
    flex-direction: column;

    &:not(:first-child) {
      margin-left: 10px;
    }

    &:nth-last-of-type(2) {
      margin-right: 40px;
    }
  }

  .fontView__selectLabel {
    margin-bottom: 6px;
    line-height: 1.42;
    color: #616161;
  }

  .formSelect {
    min-width: 120px;
    padding: 10px 34px 10px 16px; 
    box-sizing: border-box;
    border-radius: 4px;
    border-color: #E0E0E0;
    appearance: none;
    font-weight: 400;
    font-size: 14px;
    color: #111;
    background-image: url("data:image/svg+xml,%3Csvg width='10' height='6' viewBox='0 0 10 6' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M10 0.666667C10 0.847222 9.93815 1.00347 9.81445 1.13542L5.43945 5.80208C5.31576 5.93403 5.16927 6 5 6C4.83073 6 4.68425 5.93403 4.56055 5.80208L0.185547 1.13542C0.061849 1.00347 0 0.847222 0 0.666667C0 0.486111 0.061849 0.329861 0.185547 0.197917C0.309245 0.0659722 0.455729 0 0.625 0H9.375C9.54427 0 9.69076 0.0659722 9.81445 0.197917C9.93815 0.329861 10 0.486111 10 0.666667Z' fill='%238E8E8E'/%3E%3C/svg%3E%0A");
    background-position: right 19px center;
    background-repeat: no-repeat;
    background-color: #fff;
  }

  .formChecks {
    display: flex;
    align-items: flex-end;
    padding-top: 20px;
  }

  .formCheck {
    display: flex;
    align-items: center;
    position: relative;
    min-height: 20px;
    padding-left: 28px;

    &:not(:first-child) {
      margin-left: 24px;
    }
  }

  .formCheck__input {
    margin: 0;
    background-color: #fff;
  }

  .formCheck__input[type=radio] {
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
    width: 20px;
    height: 20px;
    border-radius: 50%;
    border: 1px solid #BDBDBD;
    appearance: none;
  }

  .formCheck__input:checked {
    border-color: #6F36F0;
  }

  .formCheck__input[type="radio"]:checked {
    background-image: url("data:image/svg+xml,%3Csvg width='10' height='10' viewBox='0 0 10 10' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Ccircle cx='5' cy='5' r='5' fill='%236F36F0'/%3E%3C/svg%3E");
    background-position: center;
    background-repeat: no-repeat;
  }

  .formCheck__label {
    color: #424242;
  }

  @media screen and (min-width: 460px) {
    .formChecks {
      margin-bottom: 10px;
    }
  }

  @media screen and (min-width: 768px) {
    .formSelect {
      min-width: 243px;
    }
  }
</style>