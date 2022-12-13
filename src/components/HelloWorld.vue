<template>
  <div class="hello ui segment container">
    <h3 class="ui header">簡介</h3>
    <p>    
      一般的程式課想去教你一些食譜，要做這個功能可以這樣寫、要做那個功能可以讓寫等等。
    </p>
    <p>
      但是我們現在要學的是如何用不同的方式寫同樣的程式、並且從中取捨圖你對喜歡的品味以及最容易修正錯誤的簡潔俐落寫法。
    </p>
    <p>
      例如，我們現在不是要學怎麼做一鍋為正湯，是怎麼去救煮的太鹹的味增湯。
    </p>
    <p>
      要做一件事總是有很多方法，但不是每一種方法都一樣好。
    </p>
    <p>
      有的時候不是寫得越少越好。
    </p>
    <p>
      原則上只要重複了三次的程式碼就應該獨立抽出來變成一個函式。
    </p>
    <p>
      麻瓜也能欣賞的程式設計。
    </p>

    <p>
      講授教學大綱如下：
      1. 什麼是簡潔漂亮的程式
      * 定義簡潔漂亮的程式，並舉例說明。
      * 說明簡潔漂亮的程式可以提高程式的可讀性和可維護性。
      2. 如何寫出簡潔漂亮的程式
      * 提供一些基本技巧，例如使用簡潔的變量名稱、適當地縮排、使用註釋等。
      * 說明如何運用程式設計原則，例如單一職責原則、開放封閉原則、依賴反轉原則等，來寫出簡潔漂亮的程式。
      3. 持續提升品味
      * 說明如何通過閱讀其他人的代碼、參與社區討論、和同行交流等方式來持續提升程式品味。
      * 提供一些測驗和練習題，讓學員可以實際應用所學知識，鞏固所學內容。
    </p>

    <p>
      使用簡潔的變量名稱是寫出簡潔漂亮的程式的一個基本技巧。適當地選擇變量名稱可以使程式更容易讀懂，並提高程式的可讀性和可維護性。
    </p>

    <p>
      例如，對於一個計算圓面積的函數，使用變量名稱 radius 表示圓的半徑比使用變量名稱 r 更容易讀懂。另外，避免使用模糊不清的變量名稱，例如 temp 或 a 等。
    </p>

    <p>
      總之，選擇適當的變量名稱是寫出簡潔漂亮的程式的重要技巧，可以使程式更容易讀懂，並提高程式的可讀性和可維護性。
    </p>

    <p>
      單一職責原則（Single Responsibility Principle，SRP）指的是一個模塊（類、函數、類方法等）只負責一項職責，不應該承擔多項職責。

      例如，一個函數 calculateArea 計算圓面積時，只應該負責計算圓面積，不應該負責輸出計算結果。如果在函數中還負責輸出結果，就違反了單一職責原則。
    </p>

    <pre>
    // 違反單一職責原則
    function calculateArea(radius) {
      const area = Math.PI * radius * radius;
      console.log(`半徑為 ${radius} 的圓面積為 ${area}`);
      return area;
    }
    </pre>

    <p>
      下面是一個遵循單一職責原則的例子：
    </p>

    <pre>
    // 遵循單一職責原則
    function calculateArea(radius) {
      return Math.PI * radius * radius;
    }

    function printArea(radius) {
      const area = calculateArea(radius);
      console.log(`半徑為 ${radius} 的圓面積為 ${area}`);
    }

    </pre>

    <p>
      總之，遵循單一職責原則可以使程式更容易讀懂，並提高程式的可維護性。
    </p>

    <p>
      開放封閉原則（Open/Closed Principle，OCP）指的是一個模塊應該對擴展開放，對修改關閉。例如，一個類表示一個图形，它應該允許添加新的图形類型，但不應該修改已有的图形類型。
    </p>

    <pre>
    // 違反開放封閉原則
    class Shape {
      draw() {
        // 绘制图形
      }
    }

    // 新增一种图形需要修改 Shape 類
    class Triangle extends Shape {
      draw() {
        // 绘制三角形
      }
    }
    </pre>
    
    <p>
      下面是一個遵循開放封閉原則的例子：
    </p>

    <pre>
    // 遵循開放封閉原則
    class Shape {
      draw() {
        throw new Error('必须在子類中實現 draw 方法');
      }
    }

    // 新增一种图形只需要添加新的類
    class Triangle extends Shape {
      draw() {
        // 绘制三角形
      }
    }
    </pre>

    <p>
      總之，遵循開放封閉原則可以使程式更容易擴展，並提高程式的可維護性。
    </p>


    <p>
      依賴反轉原則（Dependency Inversion Principle，DIP）指的是高層模塊不應該依賴低層模塊，二者都應該依賴抽象。例如，一個排序類只應該依賴排序接口，而不應該依賴具體的排序實現。
    </p>

    <pre>
    // 違反依賴反轉原則
    class Sorter {
      constructor(arr) {
        this.arr = arr;
      }

      sort() {
        // 使用具體的排序實現
        return this.arr.sort((a, b) => a - b);
      }
    }
    </pre>

    <p>
      下面是一個遵循依賴反轉原則的例子：
    </p>

    <pre>
    // 遵循依賴反轉原則
    class Sorter {
      constructor(arr, comparator) {
        this.arr = arr;
        this.comparator = comparator;
      }

      sort() {
        return this.arr.sort(this.comparator);
      }
    }

    const sorter = new Sorter([1, 2, 3], (a, b) => a - b);
    sorter.sort();
    </pre>

    <p>
      總之，遵循依賴反轉原則可以使程式更容易測試和維護。
    </p>

    <p>
      要寫出簡潔的好程式，需要把握的七項原則包括：
      1. 明確定義目標：確保程式有明確的目的，並能夠滿足需求。
      2. 遵循一致的命名慣例：使用易於理解和記憶的名稱來表示程式中的物件和變量。
      3. 撰寫清晰的代碼：使用易於理解的代碼撰寫方式，避免混淆和錯誤。
      4. 劃分功能：将程式拆分成較小的、功能單獨的部分，以便於維護和擴展。
      5. 遵循邏輯性：程式應該按照一定的邏輯順序來執行，使程式更容易理解和維護。
      6. 注釋代碼：為程式添加註釋，以便了解代碼的用途和運作方式。
      7. 優化代碼：對程式進行優化，以提高效率和性能。
    </p>

    <p>
      常犯的程式設計錯誤包括:
      1. 沒有明確定義目標：程式沒有明確的目的，無法滿足需求。
      2. 命名不一致：使用不一致的名稱來表示程式中的物件和變量，使程式難以理解和維護。
      3. 代碼混亂：使用難以理解的代碼撰寫方式，容易造成混淆和錯誤。
      4. 缺少註釋：沒有添加註釋，使程式的用途和運作方式難以理解。
    </p>


    <p>
      下面是一個簡單的程式碼示例，用來說明這四種錯誤:
    </p>

    <pre>
    // 第一種錯誤：沒有明確定義目標
    function calculate() {
      // 程式的目的不清晰，無法確定該函數的用途
    }

    // 第二種錯誤：命名不一致
    let x = 5;
    let y = 10;
    let result = x + y;

    // 第三種錯誤：代碼混亂
    if (result > 10) {
      console.log("大於十");
    } else {
      console.log("小於等於十");
    }

    // 第四種錯誤：缺少註釋
    function add(a, b) {
      // 沒有註釋說明函數的用途和運作方式
      return a + b;
    }
    </pre>

    <p>
      通過改進程式碼，可以避免這些錯誤:
    </p>

    <pre>
    // 明確定義目標
    function calculate(a, b) {
      // 計算兩個數字的和
      return a + b;
    }

    // 遵循一致的命名
    let num1 = 5;
    let num2 = 10;
    let sum = calculate(num1, num2);

    // 撰寫清晰的代碼
    if (sum > 10) {
      console.log("大於十");
    } else {
      console.log("小於等於十");
    }

    // 添加註釋
    function add(a, b) {
      // 計算兩個數字的和
      return a + b;
    }
    </pre>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
