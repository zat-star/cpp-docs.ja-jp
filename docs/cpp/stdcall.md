---
title: "__stdcall | Microsoft Docs"
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
  - "__stdcall_cpp"
  - "__stdcall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__stdcall キーワード [C++]"
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __stdcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `__stdcall` 呼び出し規約は、Win32 API 関数の呼び出しに使用されます。  呼び出し先がスタックを消去するため、コンパイラは **vararg** 関数を `__cdecl` にします。  この呼び出し規約を使用する関数には、関数プロトタイプが必要です。  
  
## 構文  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## 解説  
 次の一覧は、この呼び出し規約の実装例を示しています。  
  
|要素|実装|  
|--------|--------|  
|引数を渡す順序|右から左。|  
|引数渡し規約|ポインターまたは参照型が渡されない場合は、値渡し。|  
|スタック メンテナンスの役割|呼び出された関数が、自分の引数をスタックからポップします。|  
|名前装飾規約|アンダースコア \(\_\) は、名前の前に付けられます。  名前の後に、アットマーク \(@\) と、引数リストのバイト数 \(10 進数\) が続きます。  したがって、`int func( int a, double b )` として宣言された関数は次のように修飾されます: `_func@12`|  
|大文字と小文字の変換規約|なし|  
  
 [\/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) コンパイラ オプションは、明示的に異なる呼び出し規約で宣言されていないすべての関数に対して `__stdcall` を指定します。  
  
 `__stdcall` 修飾子を使用して宣言された関数は、[\_\_cdecl](../Topic/__cdecl.md) を使用して宣言された関数と同じ方法で値を返します。  
  
 ARM および x64 プロセッサでは、`__stdcall` はコンパイラによって受け入れられるか無視されます。ARM および x64 アーキテクチャでは規約によって可能な限り引数はレジスタで渡され、その後の引数はスタックで渡されます。  
  
 静的でないクラスの関数が行外で宣言されている場合、行外の宣言で呼び出し規約の修飾子を指定する必要はありません。  つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。  次のクラス定義があるとします。  
  
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
  
## 使用例  
 次の例では、**\_\_stdcall** の使用により、すべての `WINAPI` 関数型が標準呼び出しとして処理されます。  
  
```c  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## 参照  
 [引数の渡し規則と名前付け規則](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)