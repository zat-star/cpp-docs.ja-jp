---
title: "ATL と MFC の選択に関する推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d912c6cd997c23b9623d20a104327fb6e4701494
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL と MFC の選択に関する推奨事項
コンポーネントおよびアプリケーションを開発するときに 2 つの方法を選択できます: ATL および MFC (Microsoft Foundation Class ライブラリ)。  
  
## <a name="using-atl"></a>ATL を使用します。  
 ATL は、C++ では、COM コンポーネントを作成して、小さなフット プリントの管理の両方に高速で簡単な方法です。 すべての MFC を自動的に提供する組み込みの機能を必要としない場合は、コントロールを作成するのにには、ATL を使用します。  
  
## <a name="using-mfc"></a>MFC を使用します。  
 MFC では、完全なアプリケーション、ActiveX コントロール、およびアクティブ ドキュメントを作成することができます。 MFC でのコントロールを作成済みの場合は、MFC での開発を続行します。 新しいコントロールを作成する場合は、すべての MFC の組み込み機能を必要としない場合は、ATL を使用して検討してください。  
  
## <a name="using-atl-in-an-mfc-project"></a>MFC プロジェクトで ATL の使用  
 ウィザードを実行して、既存の MFC プロジェクトで ATL を使用するためのサポートを追加できます。 詳細については、「 [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ATL の概要](../atl/introduction-to-atl.md)

