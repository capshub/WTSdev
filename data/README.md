1. To load the NSE exchange symbols list into wtsdev database.

psql -U postgres -h 172.17.0.2 -d wtsdev

\copy wtst."EXCHANGE_SYMBOLS_EQUITY"("SYMBOL", "COMPANY_NAME", "SERIES", "DT_LISTING", "PAIDUP_VALUE", "MARKET_LOT", "ISIN_CODE", "FACE_VALUE") FROM '/home/wts/wtsdevgit/data/EQUITY_L.csv' DELIMITER ',' CSV HEADER;


\copy wtst."NSE_EOD_DATA"("SYMBOL", "SERIES", "OPEN", "HIGH", "LOW", "CLOSE", "LAST", "PREVCLOSE", "VOLUME", "TRADEVALUE", "DATE", "BARCOUNT", "ISINCODE", "AVERAGE") FROM '/home/wts/wtsdevgit/data/cm04JUN2021bhav.csv' DELIMITER ',' CSV HEADER;



'\\copy wtst."NSE_EOD_DATA"("SYMBOL", "SERIES", "OPEN", "HIGH", "LOW", "CLOSE", "LAST", "PREVCLOSE", "VOLUME", "TRADEVALUE", "DATE", "BARCOUNT", "ISINCODE","AVERAGE") FROM %s DELIMITER \',\' CSV HEADER '
