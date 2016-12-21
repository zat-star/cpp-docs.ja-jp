---
title: "SafeInt クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt クラス"
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: 16
caps.handback.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeInt クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

整数プリミティブを拡張して、整数オーバーフローを防止すると共に、異なる型の整数を比較できるようにします。  
  
## 構文  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### パラメーター  
  
|テンプレート|説明|  
|------------|--------|  
|T|`SafeInt` によって置き換えられる整数パラメーターまたはブール値パラメーターの型。|  
|E|エラー処理ポリシーを定義する列挙型。|  
|U|2 番目のオペランドの整数パラメーターまたはブール値パラメーターの型。|  
  
|パラメーター|説明|  
|------------|--------|  
|\[入力\] rhs|複数のスタンドアロン関数で演算子の右側の値を表す入力パラメーター。|  
|\[入力\] i|複数のスタンドアロン関数で演算子の右側の値を表す入力パラメーター。|  
|\[入力\] bits|複数のスタンドアロン関数で演算子の右側の値を表す入力パラメーター。|  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|既定のコンストラクターです。|  
  
### 代入演算子  
  
|名前|構文|  
|--------|--------|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### キャスト演算子  
  
|名前|構文|  
|--------|--------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|signed char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|\_\_int16|`operator __int16() const`|  
|unsigned \_\_int16|`operator unsigned __int16() const`|  
|\_\_int32|`operator __int32() const`|  
|unsigned \_\_int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|\_\_int64|`operator __int64() const`|  
|unsigned \_\_int64|`operator unsigned __int64() const`|  
|wchar\_t|`operator wchar_t() const`|  
  
### 比較演算子  
  
|名前|構文|  
|--------|--------|  
|\<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|\<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|\>\=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|\>\=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|\>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|\>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|\<\=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|\<\=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|\=\=|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|\=\=|`bool operator== (bool rhs) const throw()`|  
|\=\=|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|\!\=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|\!\=|`bool operator!= (bool b) const throw()`|  
|\!\=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### 算術演算子  
  
|名前|構文|  
|--------|--------|  
|\+|`const SafeInt<T,E>& operator+ () const throw()`|  
|\-|`SafeInt<T,E> operator- () const`|  
|\+\+|`SafeInt<T,E>& operator++ ()`|  
|\-\-|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|\*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|\*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|\*\=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|\/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|\/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|\/\=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|\+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|\+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|\+\=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|\-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|\-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|\-\=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### 論理演算子  
  
|名前|構文|  
|--------|--------|  
|\!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&\=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^\=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;\=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## 解説  
 `SafeInt` クラスを使用することで、数値演算での整数オーバーフローを防止できます。  たとえば、2 つの 8 ビット整数を加算するとします。一方の整数の値が 200、もう一方の整数の値が 100 です。  正しい数値演算は 200 \+ 100 \= 300 です。  ところが、8 ビット整数の制限により上位ビットが削除されるため、コンパイラが返す結果は 44 \(300 \- 2<sup>8</sup>\) になります。  この数式に依存する演算を使用した場合、常に予期しない動作が発生します。  
  
 `SafeInt` クラスは、算術オーバーフローが発生するかどうか、またはコードで 0 除算が試行されるかどうかを検証します。  どちらの場合においても、このクラスは、エラー ハンドラーを呼び出し、問題が発生する可能性があることをプログラムに警告します。  
  
 また、このクラスを使用することで、型の異なる 2 つの整数が `SafeInt` オブジェクトである限り、その 2 つの整数を比較することができます。  通常、比較を行う際には、最初に数値を同じ型に変換する必要があります。  多くの場合、ある数値を別の型の数値と比較する際、データの損失がないかどうかを確認する必要があります。  
  
 このトピックの演算子の一覧に、`SafeInt` クラスでサポートされる数値演算子と比較演算子を示しています。  ほとんどの数値演算子は、`T` 型の `SafeInt` オブジェクトを返します。  
  
 `SafeInt` と整数型の比較演算は、どちらの方向にも実行することができます。  たとえば、`SafeInt<int>(x) < y` と `y > SafeInt<int>(x)` はどちらも有効であり、同じ結果が返されます。  
  
 2 つの異なる `SafeInt` 型を使用することは、ほとんどの二項演算子においてサポートされていません。  この例の 1 つとして、`&` 演算子があります。  `SafeInt<T, E> & int` はサポートされていますが、`SafeInt<T, E> & SafeInt<U, E>` はサポートされていません。  2 番目の例の場合、コンパイラが返されるパラメーターの型を判別できないためです。  この問題を解決する方法の 1 つとして、2 番目のパラメーターを基本型にキャストできます。  同じパラメーターを使用してこれを行うには、`SafeInt<T, E> & (U)SafeInt<U, E>` を使用します。  
  
> [!NOTE]
>  ビットごとの演算を実行するには、2 つの異なるパラメーターのサイズが同じであることが必要です。  サイズが異なる場合、コンパイラは [ASSERT](../Topic/ASSERT%20\(MFC\).md) 例外をスローします。  この演算の結果は、正確性が保証されません。  この問題を解決するには、小さい方のパラメーターが大きい方のパラメーターと同じサイズになるまで、小さい方のパラメーターをキャストします。  
  
 シフト演算子の場合、テンプレートの型に存在するビットよりも多くのビットをシフトすると、ASSERT 例外がスローされます。  リリース モードでは、これによる影響はありません。  シフト演算子の場合、戻り値の型が元の型と同じであるため、2 種類の型の SafeInt パラメーターを組み合わせることができます。  演算子の右側の数値は、シフトするビット数を示すのみです。  
  
 SafeInt オブジェクトで論理比較を実行するとき、厳密に算術的な比較が実行されます。  たとえば、次の式について考えてみます。  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 1 番目のステートメントは `true` に解決されますが、2 番目のステートメントは `false` に解決されます。  0 のビットごとの否定は 0xFFFFFFFF です。  2 番目のステートメントでは、既定の比較演算子により 0xFFFFFFFF と 0xFFFFFFFF が比較され、この 2 つが等しいと判断されます。  `SafeInt` クラスの比較演算子によって、1 番目のパラメーターが符号なしであるのに対し、2 番目のパラメーターが負の値であることが判明します。  そのため、ビット表現が同一であっても、`SafeInt` の論理演算子によって、符号なし整数が \-1 より大きいことがわかります。  
  
 `SafeInt` クラスを `?:` 三項演算子と同時に使用する際には注意が必要です。  次のコード行があるとします。  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 コンパイラはこのコード行を次のように変換します。  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 `flag` が `false` の場合、コンパイラは `x` に値 \-1 を代入する代わりに例外をスローします。  このような動作を回避するための正しいコードは次のとおりです。  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` と `U` には、ブール型、文字型、または整数型を割り当てることができます。  整数型は、signed 型であるか unsigned 型であるかを問わず、8 ～ 64 ビットまでの任意のサイズに設定できます。  
  
> [!NOTE]
>  `SafeInt` クラスでは任意の種類の整数を使用できますが、unsigned 型の方が効率的に実行できます。  
  
 `E` は、`SafeInt` で使用されるエラー処理機能です。  SafeInt ライブラリには 2 つのエラー処理機能が用意されています。  既定のポリシーは `SafeIntErrorPolicy_SafeIntException` であり、エラー発生時に [SafeIntException クラス](../windows/safeintexception-class.md)例外をスローします。  もう一方のポリシーは `SafeIntErrorPolicy_InvalidParameter` であり、エラー発生時にプログラムを停止します。  
  
 エラー ポリシーをカスタマイズする方法は、2 つあります。  1 つは、`SafeInt` を作成する際に `E` パラメーターを設定する方法です。  この方法は、1 つの `SafeInt` のみに対してエラー処理ポリシーを変更する場合に使用します。  もう 1 つは、`SafeInt` ライブラリを含める前に、カスタマイズしたエラー処理クラスとして `_SAFEINT_DEFAULT_ERROR_POLICY` を定義する方法です。  この方法は、コード内のすべての `SafeInt` クラス インスタンスに対して既定のエラー処理ポリシーを変更する場合に使用します。  
  
> [!NOTE]
>  SafeInt ライブラリのエラーを処理するカスタマイズ クラスがエラー ハンドラーを呼び出したコードに制御を返さないようにしてください。  エラー ハンドラーが呼び出された後では、`SafeInt` 操作の結果は信頼できません。  
  
## 必要条件  
 **ヘッダー:** safeint.h  
  
 **名前空間:** msl::utilities  
  
## 参照  
 [Miscellaneous Support Libraries Classes](http://msdn.microsoft.com/ja-jp/406fd46e-d53f-4096-ab40-36aa754c7a5c)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeIntException クラス](../windows/safeintexception-class.md)