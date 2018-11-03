/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package com.dao;

import com.model.Student; 
import java.util.List; 
import javax.ejb.Stateless; 
import javax.persistence.EntityManager; 
import javax.persistence.PersistenceContext; 
/**
 *
 * @author USER
 */
@Stateless
public class StudentDAO implements StudentDAOLocal {

@PersistenceContext 
private EntityManager em; 
@Override 
public void addStudent(Student student) { 
em.merge(student); 
em.flush(); 
} 
@Override 
public void editStudent(Student student) { 
em.merge(student); 
em.flush(); 
} 
@Override 
public void deleteStudent(int studentId) { 
em.remove(getStudent(studentId)); 
em.flush(); 
} 
@Override 
public Student getStudent(int studentId) { 
em.flush(); 
return em.find(Student.class, studentId); 
} 
@Override 
public List<Student> getAllStudents() { 
em.flush(); 
return em.createNamedQuery("Student.getAll").getResultList(); 
} 


}