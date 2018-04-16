---
title: "コンパイラのコマンドライン構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb89aca1990d44d7ef62ea76788b38e8ffa1d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-command-line-syntax"></a>コンパイラ コマンド ラインの構文
CL のコマンド ラインでは、次の構文を使用します。  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 次の表では、CL コマンドへの入力について説明します。  
  
|入力|説明|  
|-----------|-------------|  
|*オプション*|1 つまたは複数[CL オプション](../../build/reference/compiler-options.md)です。 すべてのオプションがすべての指定したソース ファイルに適用されるに注意してください。 オプションは、スラッシュ (/) またはダッシュ (-) のいずれかによって指定されます。 場合は、オプションは、オプションと引数の間に空白が許可されているかどうかのオプションの説明のドキュメントに、引数を取ります。 (/HELP オプション) を除くオプション名では大文字小文字を区別します。 参照してください[CL オプションの指定順序](../../build/reference/order-of-cl-options.md)詳細についてはします。|  
|`file`|1 つまたは複数のソース ファイル、.obj ファイルまたはライブラリの名前。 CL は、ソース ファイルをコンパイルし、.obj ファイルとライブラリの名前をリンカーに渡します。 参照してください[CL ファイル名構文](../../build/reference/cl-filename-syntax.md)詳細についてはします。|  
|*lib*|1 つまたは複数のライブラリ名。 CL は、これらの名前をリンカーに渡します。|  
|*コマンド ファイル*|複数のオプションとファイル名を含むファイル。 参照してください[CL のコマンド ファイル](../../build/reference/cl-command-files.md)詳細についてはします。|  
|*リンクを選択します。*|1 つまたは複数[リンカー オプション](../../build/reference/linker-options.md)です。 CL は、これらのオプションをリンカーに渡します。|  
  
 コマンドラインでの文字数が 1024、オペレーティング システムで使用される制限を超えない限り、任意の数のオプション、ファイル名、およびライブラリの名前を指定できます。  
  
 Cl.exe の戻り値については、次を参照してください。 [cl.exe の戻り値](../../build/reference/return-value-of-cl-exe.md)です。  
  
> [!NOTE]
>  1024 文字のコマンドラインの入力の制限は、Windows の将来のリリースでは同じには保証されません。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)