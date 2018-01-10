---
title: "動的アクセサーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3d2e722ce96ff7a2f1add779377079a0eaecfc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-dynamic-accessors"></a>動的アクセサーの使用
動的アクセサーでは、データベース スキーマ (構造体の基になる) の知識があるない場合にデータ ソースへのアクセスを行うことができます。 OLE DB テンプレート ライブラリは、これを実現するためのいくつかのクラスを提供します。  
  
 [DynamicConsumer](http://msdn.microsoft.com/en-us/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)サンプルは、動的なアクセサー クラスを使用して列情報を取得し、動的にアクセサーを作成する方法を示しています。  
  
## <a name="using-cdynamicaccessor"></a>CDynamicAccessor を使用します。  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)データベース スキーマ (データベースの基になる構造) の知識があるない場合にデータ ソースにアクセスすることができます。 `CDynamicAccessor`メソッドは、列名、カウント、およびデータ型などの列情報を取得します。 実行時に動的にアクセサーを作成するのにには、この列の情報を使用します。 列情報が作成され、このクラスで管理されるバッファーに格納されます。 使用して、バッファーからデータを取得、 [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)メソッドです。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## <a name="using-cdynamicstringaccessor"></a>CDynamicStringAccessor を使用します。  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)と同様に動作[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)、1 つの重要な点では可します。 中に`CDynamicAccessor`、プロバイダーによって報告されたネイティブ形式でデータを要求`CDynamicStringAccessor`要求プロバイダーが文字列データとしてデータ ストアからアクセスされるすべてのデータをフェッチします。 これは、表示またはデータ ストアの内容を印刷するなど、データ ストア内の値の計算を必要としない単純なタスクに特に便利です。  
  
 使用して`CDynamicStringAccessor`列情報を取得するメソッド。 実行時に動的にアクセサーを作成するのにには、この列の情報を使用します。 列の情報は、このクラスによって作成および管理のバッファーに格納されます。 使用して、バッファーからデータを取得[cdynamicstringaccessor::getstring](../../data/oledb/cdynamicstringaccessor-getstring.md)を使用して、バッファーに格納または[cdynamicstringaccessor::setstring](../../data/oledb/cdynamicstringaccessor-setstring.md)です。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## <a name="using-cdynamicparameteraccessor"></a>Using CDynamicParameterAccessor  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)に似ていますが[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)する点を除いて、`CDynamicParameterAccessor`を呼び出すことによって設定するパラメーター情報を取得する、 [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx)インターフェイスです。 コンシューマーがこのクラスを使用するには、プロバイダーで `ICommandWithParameters` がサポートされている必要があります。  
  
 パラメーター情報は、このクラスによって作成および管理されるバッファーに格納されます。 使用してバッファーからパラメーター データを取得[cdynamicparameteraccessor::getparam](../../data/oledb/cdynamicparameteraccessor-getparam.md)と[Cdynamicparameteraccessor:getparamtype](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)です。  
  
 このクラスを使用して SQL Server のストアド プロシージャを実行し、出力パラメーター値を取得する方法の例については、サポート技術情報の記事 Q058860 の「HOWTO: Execute Stored Procedure using CDynamicParameterAccessor」を参照してください。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のマニュアルまたはで入手[http://support.microsoft.com](http://support.microsoft.com/)です。  
  
## <a name="see-also"></a>参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer サンプル](http://msdn.microsoft.com/en-us/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)