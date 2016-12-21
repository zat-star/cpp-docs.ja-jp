---
title: "プラグマ ディレクティブと __Pragma キーワード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#pragma"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#pragma ディレクティブ, C/C++"
  - "__pragma キーワード"
  - "pragma ディレクティブ (#pragma)"
  - "pragma ディレクティブ, C/C++"
  - "プラグマ"
  - "プラグマ, C/C++"
  - "プリプロセッサ"
  - "プリプロセッサ, プラグマ"
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プラグマ ディレクティブと __Pragma キーワード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プラグマ ディレクティブは、コンピューター固有またはオペレーティング システム固有のコンパイラ機能を指定します。  Microsoft コンパイラに固有の `__pragma` キーワードにより、マクロ定義内のプラグマ ディレクティブをコーディングできます。  
  
## 構文  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## 解説  
 C および C\+\+ の各実装は、そのホスト コンピューターまたはオペレーティング システムに固有の機能をいくつかサポートしています。  たとえば、一部のプログラムは、データが格納されているメモリ領域、または特定の関数がパラメーターを受け取る方法を正確に制御する必要があります。  `#pragma` ディレクティブにより、各コンパイラが C 言語および C\+\+ 言語の全体的な互換性を維持しながら、コンピューター固有の機能およびオペレーティング システム固有の機能を提供することが可能になります。  
  
 プラグマは、コンピューター固有つまりオペレーティング システム固有であり、通常はコンパイラごとに異なります。  プラグマは、新しいプリプロセッサ機能を提供するために、または実装定義の情報をコンパイラに提供するために、条件付きステートメントで使用できます。  
  
 `token-string` は、特定のコンパイラ命令と引数 \(ある場合\) を渡す一連の文字です。  シャープ記号 \(**\#**\) は、プラグマを含む行の最初の空白以外の文字である必要があります。空白文字は、シャープ記号と単語「pragma」の間に挿入できます。  `#pragma` の後に、トランスレーターによりプリプロセス トークンとして解析できるテキストを記述します。  `#pragma` の引数は、マクロの展開の対象になります。  
  
 コンパイラで認識されないプラグマが検出されると、警告が表示され、コンパイルは続行されます。  
  
 Microsoft C および C\+\+ コンパイラは、次のプラグマを認識します。  
  
||||  
|-|-|-|  
|[alloc\_text](../preprocessor/alloc-text.md)|[auto\_inline](../preprocessor/auto-inline.md)|[bss\_seg](../preprocessor/bss-seg.md)|  
|[check\_stack](../preprocessor/check-stack.md)|[code\_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|  
|[コンポーネント](../Topic/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const\_seg](../preprocessor/const-seg.md)|  
|[data\_seg](../preprocessor/data-seg.md)|[deprecated](../Topic/deprecated%20\(C-C++\).md)|[detect\_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv\_access](../preprocessor/fenv-access.md)|[float\_control](../Topic/float_control.md)|[fp\_contract](../preprocessor/fp-contract.md)|  
|[function](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include\_alias](../preprocessor/include-alias.md)|  
|[init\_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline\_depth](../preprocessor/inline-depth.md)|[inline\_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make\_public](../preprocessor/make-public.md)|  
|[managed](../preprocessor/managed-unmanaged.md)|[message](../Topic/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers\_to\_members](../Topic/pointers_to_members.md) <sup>1</sup>|  
|[pop\_macro](../Topic/pop_macro.md)|[push\_macro](../preprocessor/push-macro.md)|[region、endregion](../preprocessor/region-endregion.md)|  
|[runtime\_checks](../Topic/runtime_checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict\_gs\_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../Topic/vtordisp.md) <sup>1</sup>|  
|[警告](../preprocessor/warning.md)|||  
  
 1.  C\+\+ コンパイラでのみサポートされています。  
  
## プラグマとコンパイラのオプション  
 一部のプラグマの機能はコンパイラ オプションのものと同じです。  ソース コード内のプラグマは、コンパイラ オプションで指定された動作をオーバーライドします。  たとえば、[\/Zp8](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md) を指定している場合は、コードの特定のセクションのコンパイラ設定を [pack](../preprocessor/pack.md) でオーバーライドできます。  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## \_\_pragma\(\) キーワード  
 **Microsoft 固有の仕様**  
  
 コンパイラは、`__pragma` キーワードもサポートしています。このキーワードは `#pragma` ディレクティブと機能は同じですが、マクロ定義内でインラインで使用できます。  コンパイラはディレクティブ内のシャープ記号 \('\#'\) を[文字列化演算子 \(\#\)](../preprocessor/stringizing-operator-hash.md) として解釈するため、`#pragma` ディレクティブはマクロ定義では使用できません。  
  
 マクロでの `__pragma` キーワードの使用方法を次のコード例に示します。  このコードは、「コンパイラ COM サポートのサンプル」の ACDUAL サンプルの mfcdual.h ヘッダーからの抜粋です。  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C\/C\+\+ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)   
 [C プラグマ](../c-language/c-pragmas.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)