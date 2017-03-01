---
title: "CDaoErrorInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3a3b33f6a7b95edcb2476b03356d32e74d1b8954
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo 構造体
`CDaoErrorInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているエラー オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoErrorInfo  
{  
    long m_lErrorCode;  
    CString m_strSource;  
    CString m_strDescription;  
    CString m_strHelpFile;  
    long m_lHelpContext;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *m_lErrorCode*  
 数値の DAO エラー コードです。 「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 *m_strSource*  
 アプリケーション エラーの発生源をオブジェクトの名前。 Source プロパティは、エラーが生成されたオブジェクトを表す文字列式を示します。式は、通常、オブジェクトのクラス名です。 詳細については、DAO ヘルプの「ソース プロパティ」を参照してください。  
  
 *m_strDescription*  
 エラーに関連付けられているわかりやすい文字列。 詳細については、DAO ヘルプの「説明プロパティ」を参照してください。  
  
 *m_strHelpFile*  
 Microsoft Windows のヘルプ ファイルへの完全修飾パス。 詳細については、DAO のヘルプ トピック「HelpContext、ヘルプ ファイルのプロパティ」を参照してください。  
  
 *m_lHelpContext*  
 Microsoft Windows のヘルプ ファイルのトピックのコンテキスト ID です。 詳細については、DAO のヘルプ トピック「HelpContext、ヘルプ ファイルのプロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 MFC は、DAO クラスでオブジェクトのエラーをカプセル化しません。 代わりに、 [CDaoException](../../mfc/reference/cdaoexception-class.md)クラスは、DAO に含まれているエラーのコレクションにアクセスするためのインターフェイスを提供します。 **DBEngine**オブジェクトのすべてのワークスペースが含まれているオブジェクトを使用しています。 MFC DAO 操作がスローした場合、`CDaoException`オブジェクトをキャッチすることは、MFC は、`CDaoErrorInfo`構造体し、例外オブジェクトの格納[m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)メンバーです。 (直接 DAO を呼び出す場合は、例外オブジェクトを呼び出す必要があります[GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数を`m_pErrorInfo`)。  
  
 DAO のエラー処理の詳細については、記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。 関連情報については、DAO ヘルプの「エラー オブジェクト」を参照してください。  
  
 によって取得される情報、 [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数は、`CDaoErrorInfo`構造体。 確認、 [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)からそのデータ メンバー、`CDaoException`例外ハンドラー、または呼び出しでキャッチするオブジェクト`GetErrorInfo`から、 `CDaoException` DAO インターフェイスへの直接呼び出し中に発生したエラーを確認するために明示的に作成するオブジェクト。 `CDaoErrorInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoErrorInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)

