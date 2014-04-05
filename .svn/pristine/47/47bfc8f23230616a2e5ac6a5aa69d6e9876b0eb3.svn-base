package com.onsitesupport.dao.impl;

import java.util.Arrays;
import java.util.HashSet;
import java.util.List;
import java.util.Set;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.Query;

import org.skyway.spring.util.dao.AbstractJpaDao;
import org.springframework.dao.DataAccessException;
import org.springframework.stereotype.Repository;
import org.springframework.transaction.annotation.Transactional;

import com.onsitesupport.dao.PizzaDAO;
import com.onsitesupport.domain.Pizza;

@Repository("PizzaDAO")
@Transactional
public class PizzaDAOImpl extends AbstractJpaDao<Pizza> implements PizzaDAO {
	
	private final static Set<Class<?>> dataTypes = new HashSet<Class<?>>(Arrays.asList(new Class<?>[] { Pizza.class }));
	
	@PersistenceContext(unitName = "OnsiteSupport")
	private EntityManager entityManager;

	@SuppressWarnings("unchecked")
	@Override
	public List<Pizza> findAll() throws DataAccessException {
		Query query = createNamedQuery("findAllPizza", -1, -1);
		return query.getResultList();
	}
	
	//----------------------------------------------------------------------------------------------------------------------------------------------------------------

	@Override
	public EntityManager getEntityManager() {
		return entityManager;
	}

	@Override
	public Set<Class<?>> getTypes() {
		return dataTypes;
	}

	@Override
	public boolean canBeMerged(Pizza o) {
		return true;
	}

}
