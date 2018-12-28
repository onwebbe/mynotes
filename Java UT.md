mockito
when(configurationProvider.getObjectDefinition(isA(Class.class)).thenReturn(objDef);


mockit
mock method
new MockUp<GenericObjectToLazyBean>() {
      @mockit.Mock
      MentoringProgramMatchedParticipant transform(GenericObject eo) {
        final MentoringProgramMatchedParticipant part1 = new MentoringProgramMatchedParticipant();
        return part1;
      }
    };

mock new instance constructor
new MockUp<GenericObjectToLazyBean>() {
      @mockit.Mock
      public void $init() {}
    };

mock statis/private field when new the class
new MockUp<GenericObjectToLazyBean>() {
      @mockit.Mock
      public void $clinit() {}
    };


public void testGetValidMatchedParticipantsByUserId_for_mentor(@Mocked GOSQLGeneratorContext search)
new Verifications() {{
      List<Criterion> restirctions = new ArrayList<>();
      search.add(withCapture(restirctions));
      Assert.assertEquals(restirctions.size(), 2);
      com.successfactors.genericobject.api.sql.Criterion expected1 = Restrictions.in("mentorshipStatus", MentorshipStatusEnum.getValidStatusList());
      Assert.assertTrue(EqualsBuilder.reflectionEquals(restirctions.get(0), expected1));
      Assert.assertEquals(restirctions.get(1).getBindValues(Locale.US), Arrays.asList("cgrant1", "1234"));
      Assert.assertEquals(restirctions.get(1).getFieldsInvolved(), Arrays.asList("mentor", "programId"));
    }};


Deencapsulation class for execute classes
