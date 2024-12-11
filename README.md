## SNOW-EnviroIoT


### table ddl

````
CREATE TABLE "TASTY_BYTES_SAMPLE_DATA"."RAW_POS"."enviro" ( adjtemp VARCHAR , adjtempf VARCHAR , amplitude100 NUMBER(38, 1) , amplitude1000 NUMBER(38, 1) , amplitude500 NUMBER(38, 1) , amps NUMBER(38, 1) , cpu NUMBER(38, 1) , cpu_temp VARCHAR , diskusage VARCHAR , endtime VARCHAR , gasKO VARCHAR , highnoise NUMBER(38, 1) , host VARCHAR , host_name VARCHAR , humidity NUMBER(38, 1) , id VARCHAR , ipaddress VARCHAR , lownoise NUMBER(38, 1) , lux NUMBER(38, 1) , macaddress VARCHAR , memory NUMBER(38, 1) , midnoise NUMBER(38, 1) , nh3 NUMBER(38, 1) , oxidising NUMBER(38, 1) , pm1 NUMBER(38, 0) , pm10 NUMBER(38, 0) , pm10atmos NUMBER(38, 0) , pm1atmos NUMBER(38, 0) , pm25 NUMBER(38, 0) , pm25atmos NUMBER(38, 0) , pmper1l03 NUMBER(38, 0) , pmper1l05 NUMBER(38, 0) , pmper1l1 NUMBER(38, 0) , pmper1l10 NUMBER(38, 0) , pmper1l25 NUMBER(38, 0) , pmper1l5 NUMBER(38, 0) , pressure NUMBER(38, 1) , proximity NUMBER(38, 0) , reducing NUMBER(38, 1) , runtime VARCHAR , starttime TIMESTAMP_NTZ , systemtime TIMESTAMP_NTZ , temperature VARCHAR , temperaturef VARCHAR , uuid VARCHAR ); 

CREATE TEMP FILE FORMAT "TASTY_BYTES_SAMPLE_DATA"."RAW_POS"."temp_file_format_infer_2024-12-11T20:57:40.814Z"
	TYPE=JSON
    STRIP_OUTER_ARRAY=TRUE
    REPLACE_INVALID_CHARACTERS=TRUE
    DATE_FORMAT=AUTO
    TIME_FORMAT=AUTO
    TIMESTAMP_FORMAT=AUTO; 

COPY INTO "TASTY_BYTES_SAMPLE_DATA"."RAW_POS"."enviro" 
FROM (SELECT $1:adjtemp::VARCHAR, $1:adjtempf::VARCHAR, $1:amplitude100::NUMBER(2, 1), $1:amplitude1000::NUMBER(2, 1), $1:amplitude500::NUMBER(2, 1), $1:amps::NUMBER(2, 1), $1:cpu::NUMBER(2, 1), $1:cpu_temp::VARCHAR, $1:diskusage::VARCHAR, $1:endtime::VARCHAR, $1:gasKO::VARCHAR, $1:highnoise::NUMBER(2, 1), $1:host::VARCHAR, $1:host_name::VARCHAR, $1:humidity::NUMBER(3, 1), $1:id::VARCHAR, $1:ipaddress::VARCHAR, $1:lownoise::NUMBER(2, 1), $1:lux::NUMBER(2, 1), $1:macaddress::VARCHAR, $1:memory::NUMBER(2, 1), $1:midnoise::NUMBER(2, 1), $1:nh3::NUMBER(4, 1), $1:oxidising::NUMBER(5, 1), $1:pm1::NUMBER(1, 0), $1:pm10::NUMBER(1, 0), $1:pm10atmos::NUMBER(1, 0), $1:pm1atmos::NUMBER(1, 0), $1:pm25::NUMBER(1, 0), $1:pm25atmos::NUMBER(1, 0), $1:pmper1l03::NUMBER(1, 0), $1:pmper1l05::NUMBER(1, 0), $1:pmper1l1::NUMBER(1, 0), $1:pmper1l10::NUMBER(1, 0), $1:pmper1l25::NUMBER(1, 0), $1:pmper1l5::NUMBER(1, 0), $1:pressure::NUMBER(4, 1), $1:proximity::NUMBER(1, 0), $1:reducing::NUMBER(5, 1), $1:runtime::VARCHAR, $1:starttime::TIMESTAMP_NTZ, $1:systemtime::TIMESTAMP_NTZ, $1:temperature::VARCHAR, $1:temperaturef::VARCHAR, $1:uuid::VARCHAR
	FROM '@"TASTY_BYTES_SAMPLE_DATA"."RAW_POS"."__snowflake_temp_import_files__"') 
FILES = ('2024-12-11T20:56:15.326Z/enviro.json') 
FILE_FORMAT = '"TASTY_BYTES_SAMPLE_DATA"."RAW_POS"."temp_file_format_infer_2024-12-11T20:57:40.814Z"' 
ON_ERROR=ABORT_STATEMENT 
-- For more details, see: https://docs.snowflake.com/en/sql-reference/sql/copy-into-table

````
