---
title: "selectany | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "selectany_cpp"
  - "selectany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], selectany"
  - "selectany __declspec キーワード"
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# selectany
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 宣言されたグローバル データ項目 \(変数またはオブジェクト\) が pick\-any COMDAT \(パッケージ化された関数\) であることをコンパイラに指示します。  
  
## 構文  
  
```  
  
__declspec( selectany ) declarator  
```  
  
## 解説  
 リンク時、COMDAT の複数の定義が見つかった場合、リンカーは 1 つを選択し、残りを破棄します。  リンカー オプション [\/OPT: REF](../build/reference/opt-optimizations.md) \(最適化\) が選択されている場合、COMDAT 除去が実行されてリンカー出力のすべての参照データ項目が削除されます。  
  
 コンストラクター、および宣言におけるグローバル関数または静的メソッドによる代入は参照を作成しないため、\/OPT:REF による削除が妨げられません。  このようなコードからの副作用は、データへの他の参照が存在しない時期によって決まりません。  
  
 動的に初期化されたグローバル オブジェクトでは、`selectany` によって、参照されていないオブジェクトの初期化コードが破棄されます。  
  
 グローバル データ項目は、一度だけ EXE または DLL プロジェクトで正常に初期化できます。  `selectany` は、同じヘッダーが複数のソース ファイルに含まれる場合、ヘッダーで定義されたグローバル データの初期化中に使用できます。  `selectany` は、C コンパイラと C\+\+ コンパイラの両方で使用できます。  
  
> [!NOTE]
>  `selectany` は、外部から参照可能なグローバル データ項目の実際の初期化だけに適用できます。  
  
## 使用例  
 このコードは、`selectany` 属性の使用方法を示しています。  
  
```  
//Correct - x1 is initialized and externally visible   
__declspec(selectany) int x1=1;  
  
//Incorrect - const is by default static in C++, so   
//x2 is not visible externally (This is OK in C, since  
//const is not by default static in C)  
const __declspec(selectany) int x2 =2;  
  
//Correct - x3 is extern const, so externally visible  
extern const __declspec(selectany) int x3=3;  
  
//Correct - x4 is extern const, so it is externally visible  
extern const int x4;  
const __declspec(selectany) int x4=4;  
  
//Incorrect - __declspec(selectany) is applied to the uninitialized  
//declaration of x5  
extern __declspec(selectany) int x5;  
  
// OK: dynamic initialization of global object  
class X {  
public:  
X(int i){i++;};  
int i;  
};  
  
__declspec(selectany) X x(1);  
```  
  
## 使用例  
 このコードは、[\/OPT:ICF](../build/reference/opt-optimizations.md) リンカー オプションも使用するときに、`selectany` 属性を使用して、データ COMDAT が折りたたまれるようにする方法を示します。  データは `selectany` でマークされ、**const** \(読み取り専用\) セクションに配置されている必要があります。  読み取り専用セクションを明示的に指定する必要があります。  
  
```  
// selectany2.cpp  
// in the following lines, const marks the variables as read only  
__declspec(selectany) extern const int ix = 5;  
__declspec(selectany) extern const int jx = 5;  
int main() {  
   int ij;  
   ij = ix + jx;  
}  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)