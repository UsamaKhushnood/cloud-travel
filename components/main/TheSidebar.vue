<template>
  <div class="the-sidebar">
    <PricePerNightFilter />
    <SidebarFilters
      filter-title="Review"
      :filter-options="reviewsOptions"
      clearable="true"
      class="mt-2"
    />
    <StarRatingFilter class="mt-2" />
    <HotelNameFilter class="mt-2" />
    <SidebarFilters
      filter-title="Reservation Policy"
      :filter-options="ReservationPolicyOptions"
      class="mt-2"
    />
    <SidebarFilters
      filter-title="Meal plan"
      :filter-options="MealPlanOptions"
      collapsable="true"
      class="mt-2"
    />
    <SidebarFilters
      filter-title="Property type"
      :filter-options="PropertyTypeOptions"
      collapsable="true"
      class="mt-2"
    />
    <SidebarFilters
      filter-title="Facilities"
      :filter-options="FacilitiesOptions"
      collapsable="true"
      class="mt-2"
    />
  </div>
</template>
<script>
import PricePerNightFilter from '@/components/filters/PricePerNightFilter'
import SidebarFilters from '@/components/filters/SidebarFilters'
import StarRatingFilter from '@/components/filters/StarRatingFilter'
import HotelNameFilter from '@/components/filters/HotelNameFilter'

export default {
  components: {
    PricePerNightFilter,
    SidebarFilters,
    StarRatingFilter,
    HotelNameFilter,
  },
  data() {
    return {
      reviewsOptions: [
        { quality: 'Excellent', count: 999 },
        { quality: 'Very Good', count: 999 },
        { quality: 'Good', count: 999 },
        { quality: 'Fair', count: 999 },
        { quality: 'Poor', count: 999 },
        { quality: 'No review', count: 999 },
      ],
      ReservationPolicyOptions: [
        { quality: 'Free cancellation', count: 999 },
        { quality: 'Book now, pay later', count: 999 },
        { quality: 'Pay at hotel', count: 999 },
      ],
      MealPlanOptions: [
        { quality: 'Room only', count: 999 },
        { quality: 'Breakfast', count: 999 },
        { quality: 'Lunch', count: 999 },
        { quality: 'Dinner', count: 999 },
        { quality: 'Half board', count: 999 },
        { quality: 'Full board', count: 999 },
        { quality: 'All inclusive', count: 999 },
      ],
      PropertyTypeOptions: [
        { quality: 'Hotel', count: 999 },
        { quality: 'Hostel/Backpacker accomodation', count: 999 },
        { quality: 'Apartment', count: 999 },
        { quality: 'Aparthotel', count: 999 },
        { quality: 'Resort', count: 999 },
        { quality: 'Inn', count: 999 },
        { quality: 'Motel', count: 999 },
        { quality: 'Bed & breakfast', count: 999 },
        { quality: 'Guesthouse', count: 999 },
        { quality: 'Condo', count: 999 },
        { quality: 'All-inclusive property', count: 999 },
        { quality: 'Hostal', count: 999 },
      ],
      FacilitiesOptions: [
        { quality: 'Swimming Pool', count: 999 },
        { quality: 'Internet access', count: 999 },
        { quality: 'Non-smoking floor', count: 999 },
        { quality: 'Apartment', count: 999 },
        { quality: 'Apartment', count: 999 },
        { quality: 'Apartment', count: 999 },
        { quality: 'Apartment', count: 999 },
        { quality: 'Apartment', count: 999 },
      ],
    }
  },
}
</script>
