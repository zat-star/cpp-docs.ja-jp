---
title: "-c (リンクを行わないコンパイル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /c
dev_langs: C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 112e063af9c56ead8ae7e8f59fe88853ff55f7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-compile-without-linking"></a>/c (リンクを行わないコンパイル)
リンクの自動呼び出しをしないようにします。  
  
## <a name="syntax"></a>構文  
  
```  
/c  
```  
  
## <a name="remarks"></a>コメント  
 コンパイルする**/c** .obj ファイルだけを作成します。 リンクは、適切なファイルとビルドのリンクのフェーズを実行するオプションを明示的に呼び出す必要があります。  
  
 開発環境で作成された内部プロジェクトを使用して、 **/c**既定ではオプションです。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
-   このオプションでは、開発環境からは利用できません。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションをプログラムによって設定するには、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドラインでは、FIRST.obj および SECOND.obj オブジェクト ファイルを作成します。THIRD.obj は無視されます。  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 実行可能ファイルを作成するには、リンクを呼び出す必要があります。  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)