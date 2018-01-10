---
title: "プロジェクト ビルド エラー PRJ0008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0008
dev_langs: C++
helpviewer_keywords: PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1740b0cf1edfc90258de4fe26478298ddf2875c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0008"></a>プロジェクト ビルド エラー PRJ0008
ファイル 'file' を削除できませんでした。  
  
 **ファイルが別のプロセスによって開かれていないと、書き込み保護されていないことを確認してください。**  
  
 Visual C がすべて正常中間出力ファイルをビルド、およびワイルドカードの仕様を満たすすべてのファイルを削除、再構築中に、または削除、**消去時に削除する拡張子**プロパティに、[全般構成の設定 プロパティ ページ](../../ide/general-property-page-project.md)です。  
  
 Visual C がファイルを削除できない場合は、このエラーが表示されます。 エラーを解決するには、ファイルとそのディレクトリを書き込み可能、ビルドを実行するユーザー用です。