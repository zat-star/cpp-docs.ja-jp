---
title: "XDCMake リファレンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xdcmake
dev_langs: C++
helpviewer_keywords: xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea635d701b4dea2471067072083d9568f11f3d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="xdcmake-reference"></a>XDCMake リファレンス
xdcmake.exe は、.xdc ファイルを .xml ファイルにコンパイルされるプログラムです。 ソース コードをコンパイルしたときに、各ソース コード ファイルの Visual C コンパイラによって .xdc ファイルが作成された[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)し、ソース コード ファイルで XML タグでマークされたドキュメントのコメントが含まれている場合。  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で xdcmake.exe を使用するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
2.  開く、**構成プロパティ**フォルダーです。  
  
3.  クリックして、 **XML ドキュメント コメント**プロパティ ページ。  
  
> [!NOTE]
>  コマンドラインで xdcmake.exe オプションは、xdcmake.exe を開発環境 (プロパティ ページ) で使用すると、オプションとは異なります。 開発環境で xdcmake.exe の使用方法の詳細については、次を参照してください。 [XML ドキュメント ジェネレーター プロパティ ページ](../ide/xml-document-generator-tool-property-pages.md)です。  
  
## <a name="syntax"></a>構文  
 xdcmake`input_filename options`  
  
## <a name="parameters"></a>パラメーター  
 それぞれの文字について以下に説明します。  
  
 `input_filename`  
 Xdcmake.exe への入力として使用する .xdc ファイルのファイル名。 1 つまたは複数の .xdc ファイルを指定するか、現在のディレクトリ内のすべての .xdc ファイルを使用する *.xdc を使用します。  
  
 `options`  
 0 個以上の次:  
  
|オプション|説明|  
|------------|-----------------|  
|/?、/help|Xdcmake.exe のヘルプを表示します。|  
|/assembly:*ファイル名*|値を指定することができます、\<アセンブリ > .xml ファイル内のタグ。  既定では、値、\<アセンブリ > タグは、.xml ファイルのファイル名と同じです。|  
|/nologo|著作権メッセージを抑制します。|  
|/out:*ファイル名*|.Xml ファイルの名前を指定できます。  既定では、.xml ファイルの名前は xdcmake.exe によって処理される最初の .xdc ファイルのファイル名です。|  
  
## <a name="remarks"></a>コメント  
 Visual Studio は、プロジェクトを作成するときに、xdcmake.exe を自動的に呼び出されます。 コマンドラインで xdcmake.exe を呼び出すこともできます。  
  
 参照してください[ドキュメント コメントとして推奨されるタグ](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)ソース コード ファイルにドキュメント コメントを追加する方法についてのです。  
  
## <a name="see-also"></a>参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)