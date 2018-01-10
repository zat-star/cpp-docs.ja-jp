---
title: "-GR (実行時の型情報の有効化) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs: C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 993465bd1666e624777e52cb1c3d3a54545589dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="gr-enable-run-time-type-information"></a>/GR (ランタイム型情報の有効化)
実行時にオブジェクトの種類をチェックするコードを追加します。  
  
## <a name="syntax"></a>構文  
  
```  
/GR[-]  
```  
  
## <a name="remarks"></a>コメント  
 ときに**/GR**コンパイラは、定義では、`_CPPRTTI`プリプロセッサ マクロです。 既定では、 **/GR**にします。 **/GR-**実行時型情報が無効になります。  
  
 使用して**/GR**コンパイラがコード内のオブジェクトの種類を静的に解決できない場合。 通常必要があります、 **/GR**オプションをコードで使用される[dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)または[typeid](../../cpp/typeid-operator.md)です。 ただし、 **/GR** .rdata セクションでは、のイメージのサイズを大ききます。 コードを使用しない場合**dynamic_cast**または**typeid**、 **/GR-**小さいイメージを生成する可能性があります。  
  
 実行時型チェックの詳細については、次を参照してください。[実行時型情報](../../cpp/run-time-type-information.md)で、 *C++ 言語リファレンス*です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**言語**プロパティ ページ。  
  
4.  変更、**を有効にするランタイム型情報**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)