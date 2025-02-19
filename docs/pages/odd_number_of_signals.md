# ODD Number of Signals

## 概要

4つの入力のうち <span class="T">True</span> となる入力が奇数個であれば <span class="T">True</span> となる回路を構成する問題です。ただし青色のコンポーネントの使用数を3つ以内に抑えるという制約がついています。

## 攻略

単純に考えると、4つの入力のうち <span class="T">True</span> となる入力が
1個または3個であればよいと考えられます。
ただしこれをそのまま実装してしまうと、コンポーネントの使用数が3つを超えてしまうことが
容易に想像されます。

## 解答

<div class="spoiler-controller material-icons">&#xE5CF;開く</div>
<div class="spoiler">

XOR回路を使うことで実現することが可能です。
XOR演算の [真理値表](#truth_table) は次のようになっていました。

```truth_table
入力1, 入力2, 出力
F, F, F
T, F, T
F, T, T
T, T, F
```

入力が3つの場合は次のようになります (入力1と入力2のXORの結果を入力3とXORするのと同じです)。

```truth_table
入力1, 入力2, 入力3, 出力
F, F, F, F
T, F, F, T
F, T, F, T
T, T, F, F
F, F, T, T
T, F, T, F
F, T, T, F
T, T, T, T
```

よく観察すると、入力の数が奇数のときに出力がTrueとなっていることがわかると思います。
この性質は入力が増えても変わりません。

したがって、次のように回路を構成することができます。

![](https://gyazo.com/23a78358c48a22ebe3416c5168d95634.png)

</div>