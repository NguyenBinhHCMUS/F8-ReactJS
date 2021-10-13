# Bai 8: document.createElement() de lam gi

  1. document.createElement()
  2. document.body.appendChild()
  3. console.dir()
  4. innerText, id, className, style

```
<body>

  <div id="root"></div>

  <script>
    const root = document.getElementById('root');
    const h1 = document.createElement('h1');

    h1.innerHTML = "Bai 8";

    h1.id = 'heading';

    h1.className = 'heading';

    h1.style.color = 'red';
    h1.style = 'color: green; font-size: 5rem;'

    root.appendChild(h1);

    console.log(h1);
  </script>
</body>
```

