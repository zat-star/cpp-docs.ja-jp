---
title: "代入 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "代入演算子, オーバーロード"
  - "演算子 [C++], 割り当て"
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 代入
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

代入演算子 \(**\=**\) は、厳密には二項演算子です。  この宣言は他の二項演算子と同じですが、次の例外があります。  
  
-   非静的メンバー関数である必要があります。  非メンバー関数として宣言できる `operator=` はありません。  
  
-   派生クラスにより継承されません。  
  
-   既定の `operator=` 関数は、何も存在しない場合はコンパイラによってクラス型に対して生成できます  \(既定の `operator=` 関数の詳細については、「[メンバーごとの割り当てと初期化](http://msdn.microsoft.com/ja-jp/94048213-8b49-4416-8069-b1b7a6f271f9)」を参照してください\)。  
  
 次の例では、代入演算子を宣言する方法を示しています。  
  
```  
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 指定された引数が式の右側にあることに注意してください。  演算子は、代入の完了後に左側の値を返す代入演算子の動作を保持するオブジェクトを返します。  これにより、次のようなステートメントを記述できます。  
  
```  
pt1 = pt2 = pt3;  
```  
  
## 参照  
 [演算子のオーバーロード](../cpp/operator-overloading.md)