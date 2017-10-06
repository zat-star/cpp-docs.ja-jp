---
title: "selectany |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- selectany_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9c17221e2d0875505d9aa3f1132ea4a4b6d4c489
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="selectany"></a>selectany
**Microsoft 固有の仕様**  
  
 宣言されたグローバル データ項目 (変数またはオブジェクト) が pick-any COMDAT (パッケージ化された関数) であることをコンパイラに指示します。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec( selectany ) declarator  
```  
  
## <a name="remarks"></a>コメント  
 リンク時、COMDAT の複数の定義が見つかった場合、リンカーは 1 つを選択し、残りを破棄します。 場合、リンカー オプション[/opt:ref による](../build/reference/opt-optimizations.md)(最適化) が選択されている場合は、リンカー出力のすべての参照データ項目を削除する中間 COMDAT 除去が発生し、します。  
  
 コンストラクター、および宣言におけるグローバル関数または静的メソッドによる代入は参照を作成しないため、/OPT:REF による削除が妨げられません。 このようなコードからの副作用は、データへの他の参照が存在しない時期によって決まりません。  
  
 動的に初期化されたグローバル オブジェクトでは、`selectany` によって、参照されていないオブジェクトの初期化コードが破棄されます。  
  
 グローバル データ項目は、一度だけ EXE または DLL プロジェクトで正常に初期化できます。 `selectany` は、同じヘッダーが複数のソース ファイルに含まれる場合、ヘッダーで定義されたグローバル データの初期化中に使用できます。 `selectany` は、C コンパイラと C++ コンパイラの両方で使用できます。  
  
> [!NOTE]
>  `selectany` は、外部から参照可能なグローバル データ項目の実際の初期化だけに適用できます。  
  
## <a name="example"></a>例  
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
  
## <a name="example"></a>例  
 このコードを使用する方法を示しています、`selectany`も使用するときにデータ COMDAT が折りたたまれるようにする属性、 [/OPT:ICF](../build/reference/opt-optimizations.md)リンカー オプション。 データをマークする必要がありますに注意してください`selectany`に置かれていると、 **const** (読み取り専用) セクション。 読み取り専用セクションを明示的に指定する必要があります。  
  
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
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)
