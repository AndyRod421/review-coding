// Mock data for reviews
const mockReviews = [
  { id: 1, userId: 1, menuId: 1, review: "Great pizza! Loved the crust." },
  { id: 2, userId: 2, menuId: 1, review: "Toppings were fresh. Will order again." },
  { id: 3, userId: 3, menuId: 1, review: "Good value for money." },
  { id: 4, userId: 1, menuId: 2, review: "Delicious sauce, could use more cheese though." }
];

// Review component
const Review = ({ review }) => {
  return (
    <div className="review">
      <p className="review__text">{review.review}</p>
      <p className="review__user">User {review.userId}</p>
    </div>
  );
};

// MenuReviews component
const MenuReviews = ({ menuId }) => {
  // Mock fetching reviews for the given menuId
  const reviews = mockReviews.filter(review => review.menuId === menuId);

  return (
    <div className="menu-reviews">
      <h2 className="menu-reviews__title">Reviews</h2>
      {reviews.map(review => (
        <Review key={review.id} review={review} />
      ))}
    </div>
  );
};

.menu-reviews {
  margin-top: 20px;
}

.menu-reviews__title {
  font-size: 20px;
  margin-bottom: 10px;
}

.review {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}

.review__text {
  margin-bottom: 5px;
}

.review__user {
  font-style: italic;
  color: #666;
}

