---
title: "プロジェクト ビルド エラー PRJ0006 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0006
dev_langs: C++
helpviewer_keywords: PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ef1dff813c709a117d92abcdd7a2d4f9d3420c65
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0006"></a>プロジェクト ビルド エラー PRJ0006
一時ファイル 'file' を開けませんでした。 ファイルが存在し、ディレクトリ書き込みで保護されていないことを確認してください。  
  
 Visual C は、ビルド処理中に一時ファイルを作成できませんでした。 この原因には:  
  
-   一時ディレクトリがありません。  
  
-   読み取り専用の一時ディレクトリです。  
  
-   ディスク領域不足。  
  
-   $ (Intdir) フォルダーは読み取り専用または読み取り専用である一時ファイルが含まれています。  
  
 次のエラー PRJ0007 もこのエラーが発生: 出力ディレクトリ 'directory' を作成できませんでした。 エラー PRJ0007 は、$ (intdir) ディレクトリを作成できませんでした、一時的にファイルの作成も失敗することを意味します。  
  
 指定するには、一時ファイルが作成されます。  
  
-   応答ファイルです。  
  
-   カスタム ビルド ステップします。  
  
-   ビルド イベントです。