---
title: "__fastcall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fastcall"
  - "__fastcall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fastcall キーワード [C++]"
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# __fastcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `__fastcall` 呼び出し規約は、可能な場合に、関数への引数をレジスタに渡すことを指定します。  この呼び出し規約は x86 アーキテクチャのみに適用されます。  次の一覧は、この呼び出し規約の実装例を示しています。  
  
|要素|実装|  
|--------|--------|  
|引数を渡す順序|左から右への引数リストで見つかる最初の 2 つの DWORD またはこれより小さい引数は、ECX および EDX レジスタに渡されます。他の引数はすべてスタック上で右から左へ渡されます。|  
|スタック メンテナンスの役割|呼び出された関数によって、スタックから引数がポップされます。|  
|名前装飾規約|アット マーク \(@\) が名前の先頭に付きます。パラメーター リストでバイト数 \(10 進数\) が後続するアット マークは、名前にサフィックスとして付けられます。|  
|大文字と小文字の変換規約|大文字小文字は変換されません。|  
  
> [!NOTE]
>  将来のコンパイラ バージョンは、パラメーターを格納するために別のレジスタを使用する可能性があります。  
  
 [\/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) コンパイラ オプションを使用すると、関数が競合する属性で宣言されていない場合、または関数の名前が `main` でない場合は、モジュールの各関数は `__fastcall` としてコンパイルされます。  
  
 `__fastcall` キーワードは、ARM および x64 アーキテクチャを対象とするコンパイラによって受け取られ、無視されます。x64 チップでは、規約により、可能な場合は最初の 4 つの引数がレジスタに渡され、追加の引数はスタック上に渡されます。  詳細については、「[x64 呼び出し規約の概要](../build/overview-of-x64-calling-conventions.md)」を参照してください。  ARM チップでは、最大で 4 個の整数引数と 8 個の浮動小数点引数をレジスタに渡すことができます。追加の引数はスタック上に渡されます。  
  
 静的でないクラスの関数が行外で宣言されている場合、行外の宣言で呼び出し規約の修飾子を指定する必要はありません。  つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。  次のクラス定義があるとします。  
  
```cpp  
struct CMyClass {  
   void __fastcall mymethod();  
};  
```  
  
 ここで、  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 は次の記述と同じです。  
  
```cpp  
void __fastcall CMyClass::mymethod() { return; }  
```  
  
## 使用例  
 次の例では、関数 `DeleteAggrWrapper` にレジスタで引数が渡されます。  
  
```c  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [引数の渡し規則と名前付け規則](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)