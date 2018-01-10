---
title: "-Zp (構造体メンバーの配置) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs: C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d387e0ab020e96afb3e2975b5c8686b668cbc10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zp-struct-member-alignment"></a>/Zp (構造体メンバーの配置)
メモリに構造体のメンバーをパックする方法を制御し、モジュール内のすべての構造の同じパッキングを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションを指定すると、最初より後に、各構造体メンバーは、メンバー型のサイズのどちらかに格納または`n`-バイト境界 (ここで`n`が 1、2、4、8、または 16)、小さい方です。  
  
 使用可能な値は、次の表で説明します。  
  
 1  
 構造体は、1 バイト境界でパックします。 同じ**/Zp**です。  
  
 2  
 構造体は、2 バイト境界でパックします。  
  
 4  
 構造体は、4 バイト境界でパックします。  
  
 8  
 構造体は、(既定値) の 8 バイト境界でパックします。  
  
 16  
 構造体を 16 バイト境界でパックします。  
  
 特定のアラインメント要件がない限りは、このオプションを使用する必要があります。  
  
 使用することも[パック](../../preprocessor/pack.md)制御構造体のパッキングにします。 アラインメントの詳細については、次のトピックを参照してください。  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [__alignof 演算子](../../cpp/alignof-operator.md)  
  
-   [__unaligned](../../cpp/unaligned.md)  
  
-   [構造体の配置例](../../build/examples-of-structure-alignment.md)(x64 固有)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**コード生成**プロパティ ページ。  
  
4.  変更、**構造体メンバーの配置**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)