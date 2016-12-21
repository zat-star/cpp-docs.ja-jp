---
title: "delete 演算子 (C++) | Microsoft Docs"
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
  - "delete_cpp"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete キーワード [C++]"
  - "delete キーワード [C++], オブジェクトの解放"
  - "delete キーワード [C++], 構文"
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delete 演算子 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メモリのブロックを解放します。  
  
## 構文  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## 解説  
 *キャスト式*引数は、前に [new 演算子](../cpp/new-operator-cpp.md)で作成されたオブジェクトに割り当てられたメモリ ブロックへのポインターである必要があります。  **delete** 演算子は、型 `void` の結果を持つため、値を返しません。  例:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 **new** で割り当てられたのではないオブジェクトへのポインターに対して **delete** を使用すると、予期しない結果になります。  ただし、値 0 のポインターに対して **delete** を使用することはできます。  このプロビジョニングは、**new** が失敗時に 0 を返す場合、失敗した **new** 操作の結果を削除しても無害であることを意味します。  詳細については、「[new および delete 演算子](../cpp/new-and-delete-operators.md)」を参照してください。  
  
 **new** と **delete** 演算子は、配列も含めて、組み込み型にも使用できます。  `pointer` が配列を参照している場合は、`pointer` の前に空のかっこを記述します。  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 オブジェクトに対して **delete** 演算子を使用すると、そのメモリが解放されます。  オブジェクトを削除した後でポインターを逆参照するプログラムは、予期しない結果になるか、クラッシュする可能性があります。  
  
 C\+\+ クラス オブジェクトのメモリを解放するために **delete** を使用すると、オブジェクトのメモリを解放する前に、オブジェクトのデストラクターが呼び出されます \(オブジェクトにデストラクターが存在する場合\)。  
  
 **delete** 演算子のオペランドが変更可能な左辺値である場合、オブジェクトを削除した後のその値は未定義になります。  
  
## delete の使用  
 [delete 演算子](../cpp/delete-operator-cpp.md)には 2 つの構文バリアントがあります。単一のオブジェクトを対象とするものと、オブジェクトの配列を対象とするものです。  次のコードは、これらがどのように違うかを示します。  
  
```  
// expre_Using_delete.cpp  
struct UDType   
{  
};  
  
int main()  
{  
   // Allocate a user-defined object, UDObject, and an object  
   //  of type double on the free store using the  
   //  new operator.  
   UDType *UDObject = new UDType;  
   double *dObject = new double;  
   // Delete the two objects.  
   delete UDObject;  
   delete dObject;   
   // Allocate an array of user-defined objects on the  
   // free store using the new operator.  
   UDType (*UDArr)[7] = new UDType[5][7];  
   // Use the array syntax to delete the array of objects.  
   delete [] UDArr;  
}  
```  
  
 オブジェクトに対して配列形式の削除 \(delete \[ \]\) を使用した場合、および配列に対して非配列形式の削除を使用した場合は、未定義の結果が生成されます。  
  
## 使用例  
 **delete** の使い方の例については、「[new 演算子](../cpp/new-operator-cpp.md)」を参照してください。  
  
## delete の動作方法  
 [delete 演算子](../cpp/delete-operator-cpp.md)は、関数[演算子 delete](../Topic/operator%20delete%20Function.md) を呼び出します。  
  
 クラス型 \([class](../cpp/class-cpp.md)、[struct](../cpp/struct-cpp.md)、または [union](../cpp/unions.md)\) ではないオブジェクトでは、グローバルな delete 演算子が呼び出されます。  クラス型のオブジェクトでは、delete 式の先頭が単項スコープ解決演算子 \(::\) である場合に、deallocation 関数の名前がグローバル スコープで解決されます。  それ以外の場合、delete 演算子は、メモリ \(ポインターが null でない場合\) の割り当てを解除する前に、オブジェクトのデストラクターを呼び出します。  delete 演算子は、クラス単位で定義できます。指定のクラスの定義がない場合、グローバル delete 演算子が呼び出されます。  静的な型に仮想デストラクターが含まれるクラス オブジェクトの割り当ての解放に delete 式を使用した場合、deallocation 関数は動的な型のオブジェクトの仮想デストラクターを通じて解決されます。  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [new および delete 演算子](../cpp/new-and-delete-operators.md)   
 [operator delete 関数](../Topic/operator%20delete%20Function.md)