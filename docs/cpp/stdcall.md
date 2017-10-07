---
title: "_ _stdcall |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __stdcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __stdcall keyword [C++]
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6c4998d3f53a76246545a6290e735f52206d70ad
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="stdcall"></a>__stdcall
**Microsoft 固有の仕様**  
  
 `__stdcall` 呼び出し規約は、Win32 API 関数の呼び出しに使用されます。 コンパイラは、呼び出し先がスタックをクリーンアップ**vararg**関数`__cdecl`です。 この呼び出し規則を使用する関数には、関数プロトタイプが必要です。  
  
## <a name="syntax"></a>構文  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## <a name="remarks"></a>コメント  
 次の一覧は、この呼び出し規則の実装例を示しています。  
  
|要素|実装|  
|-------------|--------------------|  
|引数を渡す順序|右から左。|  
|引数渡し規約|ポインターまたは参照型が渡されない場合は、値渡し。|  
|スタック メンテナンスの役割|呼び出された関数が、自分の引数をスタックからポップします。|  
|名前装飾規約|アンダースコア (_) は、名前の前に付けられます。 名前の後に、アットマーク (@) と、引数リストのバイト数 (10 進数) が続きます。 したがって、`int func( int a, double b )` として宣言された関数は次のように修飾されます: `_func@12`|  
|大文字と小文字の変換規約|なし|  
  
 [/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションを指定`__stdcall`でさまざまな呼び出し規約を明示的に宣言されているすべての機能です。  
  
 使用して宣言された関数は、`__stdcall`修飾子の戻り値を使用して宣言された関数と同じ方法[_ _cdecl](../cpp/cdecl.md)です。  
  
 ARM および x64 プロセッサでは、`__stdcall` はコンパイラによって受け入れられるか無視されます。ARM および x64 アーキテクチャでは規約によって可能な限り引数はレジスタで渡され、その後の引数はスタックで渡されます。  
  
 静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規約の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。 次のクラス定義の場合、  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 this  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 は次の記述と同じです。  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>例  
 次の例では、_ _ の使用**stdcall**すべてされます`WINAPI`関数の型が標準呼び出しとして処理されます。  
  
```cpp  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>関連項目  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)   
 [キーワード](../cpp/keywords-cpp.md)
