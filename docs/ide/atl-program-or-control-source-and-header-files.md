---
title: "ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a13a4c6ddb74a6f63b5da1171a3d4360199b508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル
作成するプロジェクトに対して選択したオプションによって、Visual Studio で、ATL プロジェクトを作成するときに、次のファイルが作成されます。  
  
 これらすべてのファイル内にある、 *Projname*ディレクトリ、およびヘッダー ファイル (.h) フォルダーまたはソリューション エクスプ ローラーでフォルダーをソース ファイル (.cpp ファイル) のいずれか。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|*Projname*.h|C++ のインターフェイスの定義となインクルードで定義された項目の GUID の宣言を含むメインのインクルード ファイル。 MIDL によってコンパイル時に再生成されます。|  
|*Projname*.cpp|メイン プログラムのソース ファイルです。 実装と、インプロセス サーバー DLL のエクスポートの実装が含まれている`WinMain`ローカル サーバーです。 サービスの場合はこのさらに、すべてのサービス管理機能を実装します。|  
|Resource.h|リソース ファイルのヘッダー ファイル。|  
|StdAfx.cpp|StdAfx.h と Atlimpl.cpp ファイルが含まれます。|  
|StdAfx.h|ATL ヘッダー ファイルが含まれます。|  
  
## <a name="see-also"></a>参照  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)