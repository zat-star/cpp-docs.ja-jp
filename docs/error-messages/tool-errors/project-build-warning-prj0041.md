---
title: "プロジェクトのビルドの警告 PRJ0041 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 231b58cb0c13d1a3f87e010a5100da564b0be806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-warning-prj0041"></a>プロジェクト ビルドの警告 PRJ0041
見つかりません 'への依存関係' ファイル 'file' の依存関係。 プロジェクトがビルドできますは、このファイルが見つかるまで、最新バージョンを続けることがあります。  
  
 ファイル (リソース ファイルや.idl/.odl ファイル、たとえば、包含 include ステートメントが、プロジェクト システムを解決できませんでした。  
  
 プロジェクト システムがプリプロセッサ ステートメント (#if など) を処理できないため、問題が発生したステートメント実際にできないビルドの一部。  
  
 この警告を解決するには、.rc ファイル内のすべての不要なコードを削除するか、適切な名前のプレース ホルダー ファイルを追加します。