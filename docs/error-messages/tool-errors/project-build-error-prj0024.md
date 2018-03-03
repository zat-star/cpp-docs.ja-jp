---
title: "プロジェクト ビルド エラー PRJ0024 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf9ad974856f132599932a32b954e50453adf56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0024"></a>プロジェクト ビルド エラー PRJ0024
Unicode パス 'path' がユーザーの ANSI コード ページに変換できませんでした。  
  
 ***パス***パス文字列の元の Unicode バージョンです。 このエラーの場合が直接に変換できない ANSI 現在のシステム コード ページの Unicode のパスが存在します。  
  
 このエラーは、いないコンピューターにインストールされているコード ページを使用して、システムで開発されたプロジェクトを処理する場合に発生する可能性があります。  
  
 このエラーの解決方法では、ANSI テキストを使用するかをコンピューターに、コード ページをインストールし、システムの既定値として設定のパスを更新します。