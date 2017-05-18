---
title: "プロジェクト ビルド エラー PRJ0003 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aac7a37a94013a1acad8ee866d9ac7ce28fda94c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="project-build-error-prj0003"></a>プロジェクト ビルド エラー PRJ0003
'コマンド ライン' を起動中にエラー。  
  
 コマンド、***コマンドライン***、入力から構成されている、**プロパティ ページ**ダイアログ ボックスで、エラー コード情報はない情報が返されますが、出力ウィンドウに表示されます。  
  
 このエラーの考えられる理由:  
  
-   プロジェクトは、ATL Server に依存します。 始まる[!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]、ATL Server は Visual Studio の一部として含めるが不要になったが、CodePlex でシェアード ソース プロジェクトとしてリリースされています。 ATL Server のソース コードとツールをダウンロードするには[http://go.microsoft.com/fwlink/?LinkID=81979](http://go.microsoft.com/fwlink/?LinkID=81979)します。  
  
-   リソースが不足します。 これを解決するのには、一部のアプリケーションを閉じます。  
  
-   不十分なセキュリティ権限。 セキュリティのための十分な特権があることを確認します。  
  
-   指定された実行可能ファイルのパス[vc++ ディレクトリ](http://msdn.microsoft.com/en-us/e027448b-c811-4c3d-8531-4325ad3f6e02)を実行しようとしているツールのパスは含まれません。  
  
-   メイクファイル プロジェクトの場合は、いずれかで実行するコマンドがない**ビルド コマンドライン**または**リビルド コマンドライン**します。  
  
## <a name="see-also"></a>関連項目  
 [プロジェクト ビルド エラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
