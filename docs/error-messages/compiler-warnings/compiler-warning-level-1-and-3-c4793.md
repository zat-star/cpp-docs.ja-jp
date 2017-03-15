---
title: "コンパイラの警告 (レベル 1 および 3) C4793 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4793
dev_langs:
- C++
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: 28
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: a217d2074affa1598aef93882fb299c6fcdef5a6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-and-3-c4793"></a>コンパイラの警告 (レベル 1 および 3) C4793
'function': 関数は、ネイティブ コードとしてコンパイルされます: '理由'  
  
 コンパイラがコンパイルできません。*関数*をマネージ コードにも、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを指定します。 代わりに、コンパイラは警告 C4793 と、継続タスクの説明メッセージが出力し、コンパイル*関数*ネイティブ コードにします。 継続メッセージに含まれる、*理由*理由を説明するテキスト*関数*にコンパイルできない`MSIL`します。  
  
 これは、レベル 1 の警告を指定すると、`/clr:pure`コンパイラ オプション。  **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で使用されなくなりました。  
  
 次の表は、メッセージを可能な継続タスクを一覧表示します。  
  
|理由のメッセージ|コメント|  
|--------------------|-------------|  
|アラインされたデータ型は、マネージ コードではサポートされません。|CLR できる必要があります、必要に応じて、データを割り当てる場合に、データがなどの宣言に揃えられます可能しない可能性もある[_ _m128](../../cpp/m128.md)または[align](../../cpp/align-cpp.md)します。|  
|マネージ コードでは、'_imagebase' を使用する関数はサポートされていません|`__ImageBase`通常は DLL を読み込む低レベルのネイティブ コードからのみで使用される特殊なリンカー記号です。|  
|は、可変引数はサポートされていない、'/clr' コンパイラ オプション|ネイティブ関数を持つマネージ関数を呼び出すことはできません[可変個引数リスト](../../cpp/functions-with-variable-argument-lists-cpp.md)(varargs) 関数は、さまざまなスタック レイアウトの条件を持つためです。 ただし、指定した場合、`/clr:pure`コンパイラ オプション、可変個引数のリストは、アセンブリがマネージ関数しか含むことがサポートされます。 詳細については、次を参照してください。[純粋で検証可能なコード (C + +/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)します。|  
|64 ビット CLR では、_ _ptr32 修飾子で宣言されたデータはサポートされません。|ポインターは、現在のプラットフォームのネイティブ ポインターと同じサイズである必要があります。 詳細については、次を参照してください。 [_ _ptr32、 \__ptr64](../../cpp/ptr32-ptr64.md)します。|  
|32 ビット CLR では、_ _ptr64 修飾子で宣言されたデータはサポートされません。|ポインターは、現在のプラットフォームのネイティブ ポインターと同じサイズである必要があります。 詳細については、次を参照してください。 [_ _ptr32、 \__ptr64](../../cpp/ptr32-ptr64.md)します。|  
|マネージ コードでは、1 つまたは複数の組み込み関数はサポートされていません|組み込みの名前は、メッセージが生成された時点では使用できません。 ただしの通常このメッセージの原因となる組み込みとは、低レベルのマシン命令ことを表します。|  
|マネージ コードでは、インラインのネイティブ アセンブリ ('_ _asm') はサポートされていません|[インライン アセンブラー コード](../../assembler/inline/asm.md)管理ことはできませんが、任意のネイティブ コードを含めることができます。|  
|_ _Clrcall 非仮想関数のサンクはネイティブとしてコンパイルする必要があります。|以外の[_ _clrcall](../../cpp/clrcall.md)仮想関数のサンクがアンマネージ アドレスを使用する必要があります。|  
|'_Setjmp' を使用して関数はネイティブとしてコンパイルする必要があります。|CLR は、プログラムの実行を制御できる必要があります。 ただし、 [setjmp](../../cpp/using-setjmp-longjmp.md)関数は、保存とレジスタや実行状態などの低水準の情報を復元によって通常のプログラムの実行をバイパスします。|  
  
## <a name="example"></a>例  
 次の例では、C4793 を生成します。  
  
```  
// C4793.cpp  
// compile with: /c /clr /W3   
// processor: x86  
int asmfunc(void) {   // C4793, compiled as unmanaged, native code  
   __asm {  
      mov eax, 0  
   }  
}  
```  
  
```Output  
warning C4793: 'asmfunc' : function is compiled as native code:  
        Inline native assembly ('__asm') is not supported in managed code  
```  
  
## <a name="example"></a>例  
 次の例では、C4793 を生成します。  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
```Output  
warning C4793: 'f' : function is compiled as native code:  
        A function using '_setjmp' must be compiled as native  
```
