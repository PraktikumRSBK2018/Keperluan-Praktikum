/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package com.dao;

import javax.ejb.Stateless;
import com.model.Login; 
import java.util.List;  
import javax.persistence.EntityManager; 
import javax.persistence.PersistenceContext; 

/**
 *
 * @author USER
 */
@Stateless
public class LoginDAO implements LoginDAOLocal {
@PersistenceContext 
private EntityManager em; 
@Override 
public boolean checkUser(String userName, String password) { 
List<Login> s = (List<Login>)em.createQuery("select e from Login e where e.userName='"+userName+"' and e.password='"+password+"'").getResultList(); 
System.out.println("is list empty ?"+s.isEmpty()+" for the"+userName+" and "+password);
if(!s.isEmpty()) 
return true; 
else 
return false; 
} 
    // Add business logic below. (Right-click in editor and choose
    // "Insert Code > Add Business Method")
}
