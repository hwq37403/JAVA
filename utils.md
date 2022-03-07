### **MD5加密**


```JAVA
import sun.misc.BASE64Encoder;
import sun.security.provider.MD5;

import java.io.UnsupportedEncodingException;
import java.math.BigInteger;
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;

public class MyMD5 {

    public String EncoderByMd5(String str) throws NoSuchAlgorithmException, UnsupportedEncodingException {
        MessageDigest md5=MessageDigest.getInstance("MD5");
        BASE64Encoder base64en=new BASE64Encoder();
        String newstr=base64en.encode(md5.digest(str.getBytes("utf-8")));
        return newstr;
    }

    public static String getMD5String(String str){
        try{
        MessageDigest md= MessageDigest.getInstance("MD5");
        md.update(str.getBytes());
        return new BigInteger(1,md.digest()).toString(16);}
        catch (Exception e) {
            e.printStackTrace();
            return null;
        }
        }
    }


```