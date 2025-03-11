<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Show One Item by Data Attribute</title>
    <style>
      ul {
        list-style: none;
        padding: 0;
      }
      li {
        margin: 4px 0;
      }
      #item-list li {
        border: solid 1px;
      }
      .page-buttons li {
        display: inline-block;
        margin-right: 5px;
      }
      .page-buttons a.navo {
        cursor: pointer;
        color: blue;
        background: #000;
        text-decoration: underline;
      }
    </style>
  </head>
  <body>
    <ul class="page-buttons">
      <li><a href="#" data-index="0">1</a></li>
      <li><a href="#" data-index="1">2</a></li>
      <li><a href="#" data-index="2">3</a></li>
      <li><a href="#" data-index="3">4</a></li>
      <li><a href="#" data-index="4">5</a></li>
      <li><a href="#" data-index="5">6</a></li>
      <li><a href="#" data-index="6">7</a></li>
      <li><a href="#" data-index="7">8</a></li>
    </ul>

    <ul id="item-list">
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
      <li>Item 4</li>
      <li>Item 5</li>
      <li>Item 6</li>
      <li>Item 7</li>
      <li>Item 8</li>
    </ul>

    <script>
      const buttons = document.querySelectorAll(".page-buttons a");
      const items = document.querySelectorAll("#item-list li");

      function showOnlyItem(index) {
        items.forEach((item, i) => {
          item.style.display = i === index ? "list-item" : "none";
          item.style.width = i === index ? "80%" : "100%";
        });
      }

      buttons.forEach((button) => {
        button.addEventListener("click", (e) => {
          e.preventDefault();
          const index = parseInt(button.dataset.index);
          showOnlyItem(index);

          // 모든 버튼에서 클래스 제거 후, 현재 버튼에 추가
          buttons.forEach((btn) => btn.classList.remove("navo"));
          button.classList.add("navo");
        });
      });
    </script>
  </body>
</html>
